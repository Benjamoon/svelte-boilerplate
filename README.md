# svelte-boilerplate

Most simple svelte boilerplate... 

Heres a few code snippets i like to use often too :)

## Pocketbase store (pb.js)
```
import PocketBase from 'pocketbase';
import { writable } from 'svelte/store';

export const pb = new PocketBase('http://localhost:8090'); 

export const user = writable(pb.authStore.model);

pb.authStore.onChange((auth) => {
    user.set(pb.authStore.model);
});
```

## Path watcher (super simple router) (path.js)
```
import { writable } from "svelte/store"

export const path = writable(window.location.pathname)

window.addEventListener('navigate', (event) => {
    path.set(window.location.pathname)
});

export const navigate = (path)=>{
    window.location.pathname = path
}
```
