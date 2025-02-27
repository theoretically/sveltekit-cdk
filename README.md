# SvelteKit CDK Adapter

## WARNING: Not for production use!!

This repo contains tooling to deploy SvelteKit sites to AWS using CDK.

Package structure is based on assumption that SvelteKit site is part or a larger system,
hosted on AWS and deployed with CDK.

Tools are split to two packages: **adapter** that plugs into the sveltekit project, and 
**constructs** that are imported to CDK project to integrate SvelteKit site to other parts
of your system.

- Adapter: **[@sveltekit-cdk/adapter](https://github.com/juranki/sveltekit-cdk/tree/main/packages/adapter#readme)** [![npm version](https://badge.fury.io/js/@sveltekit-cdk%2Fadapter.svg)](https://badge.fury.io/js/@sveltekit-cdk%2Fadapter)
  - [x] makes sveltekit artifacts available to be consumed in CDK stacks
  - [ ] optionally deploys a CDK stack after producing the artifacts
- CDK v1 constructs: **[@sveltekit-cdk/constructs](https://github.com/juranki/sveltekit-cdk/tree/main/packages/constructs#readme)** [![npm version](https://badge.fury.io/js/@sveltekit-cdk%2Fconstructs.svg)](https://badge.fury.io/js/@sveltekit-cdk%2Fconstructs) 
  - [x] CloudFront distribution for static content
  - [x] Lambda@Edge renderer attached to the distribution
  - [x] Lambda renderer behind API Gateway HTTP API
- CDK v2 constructs: **[@sveltekit-cdk/constructsv2](https://github.com/juranki/sveltekit-cdk/tree/main/packages/constructsv2#readme)** [![npm version](https://badge.fury.io/js/@sveltekit-cdk%2Fconstructsv2.svg)](https://badge.fury.io/js/@sveltekit-cdk%2Fconstructsv2)
  - [x] CloudFront distribution for static content
  - [x] Lambda@Edge renderer attached to the distribution
  - [x] Lambda renderer behind API Gateway HTTP API

## Howto

**TODO: fill in details**

1. init sveltekit project
2. init cdk project
3. add adapter to sveltekit project and point it to cdk project
4. add constructs to cdk project
5. optionally edit cdk stacks to
   - hook site up with other resources
   - add custom domain and certificate
   - adjust capacity allocation
   - ...

## Status

- In initial development, API IS NOT STABLE!
- I feel quite confident about overall structure
- Areas of uncertainty that are likely to cause significant changes (== opinions, feedback and advice appreciated)
  - how to design constructs to be both intuitive and flexible; how much flexibility is really needed
  - dependency management of constructs: cdk moves fast, v1 and v2 have different approaches to packaging and versioning 
  - adapter interface of sveltekit migth still change a little

### Links

- [API reference](https://juranki.github.io/sveltekit-cdk/)
- [@sveltekit-cdk/adapter changelog](https://github.com/juranki/sveltekit-cdk/blob/main/packages/adapter/CHANGELOG.md)
- [@sveltekit-cdk/constructs changelog](https://github.com/juranki/sveltekit-cdk/blob/main/packages/constructs/CHANGELOG.md)
