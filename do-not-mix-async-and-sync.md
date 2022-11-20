# Do Not Mix async and sync(Why you should use async keyword)
```ts
const CACHE: {[url: string] : string} = {};

function fetchWithCache(url: string, callback: (result: string) => void) {
   
  if (url in CACHE) {
    callback(CACHE[url]);
  } else {
    doFetch(url, (r: string) => {
      CACHE[url] = r;
      callback(r);
    });
  }
}

function doFetch(url: string, callback: (result: string) => void) {
  Promise.resolve('200').then(value => {
    callback(value);
  });
}

let currentStatus = '';

function fetchCurrentApi(url: string) {
  fetchWithCache(url, (result)=> {
    currentStatus = 'success';
  });

  currentStatus = 'loading';
}

const API = 'https://someapi.com';

fetchCurrentApi(API);

setTimeout(() => {
  console.log(currentStatus);
  fetchCurrentApi(API);
  setTimeout(() => {
     console.log(currentStatus);
  }, 1000);
}, 1000);
```