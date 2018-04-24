![ARK Core](https://i.imgur.com/1aP6F2o.png)

# ARK Core

## Installation

```bash
yarn add @arkecosystem/core
```

## Quickstart

### Installation
- Clone repo
- Windows PreRequsities:
  - install https://slproweb.com/download/Win64OpenSSL-1_0_2m.exe
  - `npm install --global --production windows-build-tools` (pay atention to have correct msbuild tools).
  - if there is still a build error "missing CL.exe" --> create an empty C++ project in Microsoft Visual Studio. If missing it will reinstall correct build tools.

- `npm install -g nodemon`
- `npm install`
- Check `config/___network___/server` (above all database connection parameters)
  - Change database engine if required - set `db.dialect` to one of: `sqlite`, `mysql`, `mssql` or `postgres`
  - Install package (E.g. `npm install ...`: `sqlite3`, `mysql2`, `tedious` or `pg pg-hstore`)
    - sqlite also supports in memory. This can be done by setting uri to: `sqlite://:memory:`
  - The `docker-compose up` could be used to create and start the PostgreSQL database.
- Start relay: `npm run start:devnet` to start devnet (use mainnet or testnet as well)
- Start forger: `npm run forge:devnet` (check for passphrases in `config/devnet/delegate`)

## TODO:

  - [x] Rebuild devnet
  - [x] Rebuild mainnet
  - [x] Start independant testnet
  - [x] Fast rebuild (with automatic switch to full rebuild when rebuild is close to network height)
  - [x] Awesome logging
  - [x] Rotating and compressing log
  - [x] Constants in config file, with progressive fork rules (to be improved to take into wallet rounds instead of height)
  - [x] Support for MySQL (not tested)
  - [x] Support for PostgreSQL
  - [x] Support for SQLite3
  - [x] Support for MsSQL (not tested)
  - [x] Internal API for forger
  - [x] Forger on independent core
  - [x] BIP38 encryption of delegate passphrase
  - [x] Connect forger to Transaction Pool
  - [x] Finite State Machine
  - [x] API to interact with state machine

Upcoming:
  - [ ] Testing (20%)
  - [ ] P2P API compatibility (95%)
  - [ ] Transaction Pool (80%)
  - [ ] New P2P API (0%)
  - [ ] HardFork management (30%)
  - [ ] Documentation

## Development

### Testing

To run the tests:
 - `npm test` to test everything.
 - `npm run test:api` to execute the API tests only.
 - `npm run test:unit` to execute the unit tests only.

To watch the source files and run the tests on changes:
 - `npm run test:watch` to test everything.
 - `npm run test:api:watch` to execute the API tests only.
 - `npm run test:unit:watch` to execute the unit tests only.

To calculate coverage:
 - `npm run coverage` would show the report of all tests.

## Security

If you discover a security vulnerability within this package, please send an e-mail to security@ark.io. All security vulnerabilities will be promptly addressed.

## Credits

- [François-Xavier Thoorens](https://github.com/fix)
- [Kristjan Košič](https://github.com/kristjank)
- [Brian Faust](https://github.com/faustbrian)
- [All Contributors](../../contributors)

## License

[MIT](LICENSE) © [ArkEcosystem](https://ark.io)