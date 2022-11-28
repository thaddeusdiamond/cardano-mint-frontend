# cardano-nft-js-toolkit

### This package provides a simple example of how to use [Lucid](https://github.com/Berry-Pool/lucid) to build a frontend dApp for NFT minting

## Quickstart

Prerequisites:

* [node](https://nodejs.org/en/download/)>=16.15.1
* [npm](https://www.npmjs.com/package/npm)>=8.12.0
* [static-server](https://www.npmjs.com/package/static-server)>=2.2.1 (for local serving)

You must update your secrets in a root file called `src/js/secrets.js`. The file should contain the following format:

    // Blockfrost.io keys (used across pages)
    export const BLOCKFROST_PROJ = "<BLOCKFROST_PROJ>"
    export const TEST_BLOCKFROST_PROJ = "<TEST_BLOCKFROST_PROJ>"
    // Used for token-gating throughout
    export const AUTHORIZATION_MINS = {
      "<GATEKEEPING_NFT_POLICY>": <MIN_TO_USE_TOOLS>
    };
    // Used in nft-creator.js
    export const MAX_QUANTITY = <MAX_QUANTITY_OF_FTS_FOR_1OF1_MINTER>;

:warning: DO NOT COMMIT SECRETS TO THIS REPOSITORY!!

Before your very first run (or any time you change the dependencies), you MUST run:

    npm i

To install all the required dependencies.

The sample module in ``src/js/tools/drop-payment.js`` contains functions that are bound to the DOM in ``src/static/drop-payment.html``. To build the required JS modules into a single webpack JS, run:

    npm run build

Then, serve the ``src/static/drop-payment.html`` using a web application server you prefer.  We recommend (for quickstarts, not production), [static-server]().  To install this, run:

    npm i static-server

Then, to serve the pages:

    cd dist/
    static-server

## Build

The expected output of this package is a set of Javascript and WASM resources in ``dist/`` for deployment to a production dApp.  To compile these, run this from project root:

    npm run build

To completely reset the cache and prior builds, simply run:

    rm -fr dist/

## Tests

Tests can be run through ``npm`` in the root directory:

    npm run test
