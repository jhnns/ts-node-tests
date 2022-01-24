# ts-node-tests

This repo demonstrates a problem when using `--loader ts-node/esm`.

## Steps to reproduce

- Run `npm start`
- You'll see:

```sh
> ts-node-tests@1.0.0 start
> cross-env NODE_OPTIONS='--loader ts-node/esm' http-server

(node:25506) ExperimentalWarning: --experimental-loader is an experimental feature. This feature could change at any time
(Use `node --trace-warnings ...` to show where the warning was created)
/ts-node-tests/node_modules/ts-node/dist-raw/node-esm-default-get-format.js:76
        throw new ERR_UNKNOWN_FILE_EXTENSION(ext, fileURLToPath(url));
              ^
TypeError: ERR_UNKNOWN_FILE_EXTENSION is not a constructor
    at defaultGetFormat (/ts-node-tests/node_modules/ts-node/dist-raw/node-esm-default-get-format.js:76:15)
    at defer (/ts-node-tests/node_modules/ts-node/src/esm.ts:214:7)
    at /ts-node-tests/node_modules/ts-node/src/esm.ts:236:24
    at Generator.next (<anonymous>)
    at /ts-node-tests/node_modules/ts-node/dist/esm.js:8:71
    at new Promise (<anonymous>)
    at __awaiter (/ts-node-tests/node_modules/ts-node/dist/esm.js:4:12)
    at getFormat (/ts-node-tests/node_modules/ts-node/dist/esm.js:94:16)
    at /ts-node-tests/node_modules/ts-node/src/esm.ts:172:14
    at Generator.next (<anonymous>)
```