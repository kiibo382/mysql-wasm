# MySQL Wasm

## Quickstart

```sh
cd packages/runtime && npx serve
```

Go to http://localhost:3000 and have fun!

## Packages

This repo is split into three packages that build up the environment for running MySQL in the browser.

- [runtime](/packages/runtime): The v86 emulator that starts the `buildroot` image
- [Buildroot](/packages/buildroot): Scripts to build the CPU and memory snapshot run by v86.
- [Websockproxy](/packages/websockproxy): Networking

## Acknowledgements

- [postgres-wasm](https://github.com/snaplet/postgres-wasm) is a PostgreSQL server instance running in a virtual machine running in the browser by Supabase & Snaplet.
