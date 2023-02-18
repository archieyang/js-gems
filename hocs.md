# Higher-Order Components

[Effective Higher-Order Components](https://www.bbss.dev/posts/effective-hocs/)

```tsx
interface HOC<T> {
  (Component: React.ComponentType<T>): (props: T) => JSX.Element;
}

const withColoredPadding =
  (color: string) => (Component: any) => (props: any) => {
    return (
      <div style={{ padding: 10, backgroundColor: color }}>
        <Component {...props} />
      </div>
    );
  };

function reduceHOC<T>(...hocs: HOC<T>[]): HOC<T> {
  return hocs.reduce((prev, current) => {
    return (Component) => {
      return current(prev(Component));
    };
  });
}

function applyHOC<T>(...hocs: HOC<T>[]) {
  const reduced = reduceHOC(...hocs);
  return (Component: React.ComponentType<T>) => {
    const Wrapped = reduced(Component);
    return (props: T & JSX.IntrinsicAttributes) => {
      return <Wrapped {...props} />;
    };
  };
}

const Content = () => {
  return <div> Content Area</div>;
};

export default applyHOC(
  withColoredPadding("green"),
  withColoredPadding("red")
)(Content);
```
