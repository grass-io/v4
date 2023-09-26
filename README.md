# Squads V4 program

The Squads V4 program is the latest release of the Squads multisig protocol. This program was designed to be used as a solution for on-chain treasury and smart contract management on Solana, as well as for a variety of Fintech applications that require strong security fundamentals.

## Content

This repository contains:

 - The Squads Protocol V4 Solana program.
 - The `@sqds/multisig` Typescript SDK to interact with the Squads V4 program.
 - The `squads-multisig` crate to interact with the Squads V4 program in Solana programs as well as Rust client applications.

## Smart contract Adresses

The Squads Protocol V4 program is deployed to:

 - Solana Mainnet-beta: `SQDS4ep65T869zMMBKyuUq6aD6EgTu8psMjkvj52pCf`
 - Solana Devnet: `SQDS4ep65T869zMMBKyuUq6aD6EgTu8psMjkvj52pCf`

Both deployments can be verified using the [Ellipsis Labs verifiable build](https://github.com/Ellipsis-Labs/solana-verifiable-build) tool.

## Responsibility

By interacting with this program, users acknowledge and accept full personal responsibility for any consequences, regardless of their nature. This includes both potential risks inherent to the smart contract, also referred to as program, as well as any losses resulting from user errors or misjudgment.

### Compiling and testing

You can compile the code with Anchor.
```
anchor build
```
If you do not have the Solana Anchor framework CLI installed, you can do so by following [this guide](https://www.anchor-lang.com/docs/installation).

To deploy the program on a local validator instance for testing or development purposes, you can create a local instance by running this command from the [Solana CLI](https://docs.solana.com/cli/install-solana-cli-tools).
```
solana-test-validator
```
To run the tests, first install the node modules for the repository.
```
yarn
```
or 
```
npm install
```
And run these tests with this command:
```
yarn test
```

### Verifying the code
First, compile the programs code from the `Squads-Protocol/v4` Github repository to get its bytecode.
```
git clone https://github.com/Squads-Protocol/v4.git
```

```
anchor build
```
Now, install the [Ellipsis Labs verifiable build](https://crates.io/crates/solana-verify) crate.
```
cargo install solana-verify
```
Get the executable hash of the bytecode from the  Squads program that was compiled.
```
solana-verify get-executable-hash target/deploy/multisig.so
```
Get the hash from the bytecode of the on-chain Squads program you want to verify.
```
solana-verify get-program-hash -u <cluster url> SQDS4ep65T869zMMBKyuUq6aD6EgTu8psMjkvj52pCf
```
If the hash outputs of those two commands match, the code in the repository matches the on-chain programs code.


## Usage
Instructions on how to interact with the Squads V4 program can be found in [the Squads developer portal](https://developers.squads.so).

## Security
The Squads protocol has undergone various independent audits by leading cybersecurity and blockchain smart contract auditing firms.


## License

The primary license for Squads Multisig Program V4 is the Business Source License 1.1 (`BUSL-1.1`), see [LICENSE](./LICENSE). The following exceptions are not licensed under the BULS-1.1, but are licensed separately as follows:

- The file <https://github.com/Squads-Protocol/v4/blob/main/programs/multisig/src/utils/system.rs> is derived from code released under the [Apache 2.0 license](https://github.com/coral-xyz/anchor/blob/master/LICENSE) at <https://github.com/coral-xyz/anchor/blob/714d5248636493a3d1db1481f16052836ee59e94/lang/syn/src/codegen/accounts/constraints.rs#L1126-L1179>.
- The file <https://github.com/Squads-Protocol/v4/blob/main/programs/multisig/src/utils/small_vec.rs> is derived from code released under both the [Apache 2.0 license](https://github.com/near/borsh-rs/blob/master/LICENSE-APACHE) and the [MIT license](https://github.com/near/borsh-rs/blob/master/LICENSE-MIT) at <https://github.com/near/borsh-rs/blob/master/borsh/src/de/hint.rs> and <https://github.com/near/borsh-rs/blob/master/borsh/src/ser/mod.rs>.

To the extent that each such file incorporates code from another source, such code is licensed under its respective open source license as provided above, and the original open source code is copyrighted by its respective owner as provided above.
