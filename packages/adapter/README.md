# @sveltekit-cdk/adapter

[![npm version](https://badge.fury.io/js/@sveltekit-cdk%2Fadapter.svg)](https://badge.fury.io/js/@sveltekit-cdk%2Fadapter)

## WARNING: Not for production use!!

## Intro

Plug this adapter to your SvelteKit project to
copy artifacts to CDK stack, and optionally deploy thereafter.

Use the [@sveltekit-cdk/construct](https://github.com/juranki/sveltekit-cdk/tree/main/packages/constructs#readme)
to specify how SvelteKit is integrated to your
stack.

## Instructions

1. In sveltekit project:
    ```bash
    > npm i -s @sveltekit-cdk/adapter
    ```
2. In `svelte.config.js`
    ```javascript
    import preprocess from 'svelte-preprocess';
    import { AwsServerlessAdapter } from '@sveltekit-cdk/adapter'

    const config = {
        preprocess: preprocess(),

        kit: {
            // hydrate the <div id="svelte"> element in src/app.html
            target: '#svelte',
            adapter: AwsServerlessAdapter({
                cdkProjectPath: '../the-cdk-project'
            })
        }
    };

    export default config;
    ```


### Links

- [API reference](https://juranki.github.io/sveltekit-cdk/modules/_sveltekit_cdk_adapter.html)
- [Changelog](./CHANGELOG.md)

