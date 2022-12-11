# SPK-STREAM

# Smart Contract
## Require

➜ rustc --V  
rustc 1.65.0 (897e37553 2022-11-02) or higher

➜ cargo --version  
cargo 1.65.0 (4bc8f24d3 2022-10-20) or higher

## Build

➜ cargo build --target wasm32-unknown-unknown --release

➜ near dev-deploy ./target/wasm32-unknown-unknown/release/\*\*\*.wasm

# BackEnd