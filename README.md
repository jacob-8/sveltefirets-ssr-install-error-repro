# Using sveltefirets from installed package repro

- `npm i -D sveltefirets`
- `npm run dev` and open in the browser to see the failure of trying to use the `Collection` component (error below). Note that if things were working properly, no data would come as the API key here is restricted to certain URLs but the browser should just return the normal error from Firebase: "Missing or insufficient permissions" - it will only do that if you navigate to the About page and then back to home which triggers client-side usage. When I try this simple example with an unrestricted API key on localhost, things work well client-side but not server-side. And then when I copy in the lib to a `src/sveltefire` folder as described in my docs, everything is good. Things are ignored on the server and work client-side.

## Error

```
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/idb/lib/idb.mjs?v=3320872d:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/@firebase/installations/dist/index.esm2017.js?v=3320872d:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/@firebase/performance/dist/index.esm2017.js?v=3320872d:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/firebase/performance/dist/index.esm.js?v=3320872d:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/sveltefirets/perf.js:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/sveltefirets/stores.js:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /node_modules/sveltefirets/components/Collection.svelte:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
7:38:06 AM [vite] Error when evaluating SSR module /src/routes/index.svelte:
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)

IDBIndex is not defined
ReferenceError: IDBIndex is not defined
    at /node_modules/idb/lib/idb.mjs?v=3320872d:87:38
    at instantiateModule (C:\dev\test-my-collection\node_modules\vite\dist\node\chunks\dep-1be34a63.js:75018:15)
```