learner: tungleanh.testnet 
advisor: dev-1669018198583-29903555965521

token.spk-stream.testnet
app.spk-stream.testnet
stake.spk-stream.testnet

cargo build --target wasm32-unknown-unknown --release

near dev-deploy ./target/wasm32-unknown-unknown/release/fungible_token.wasm

->>>>>>>> token
token contract: dev-1669021473407-34726394271280
near call dev-1669021473407-34726394271280 new_default_meta '{"total_supply": "100000000000000000000000000000"}' --accountId dev-1669021473407-34726394271280

->>>>>>>> stake
stake contract: dev-1669021948335-14262252549691
near call dev-1669021948335-14262252549691 new '{"_token_address": "dev-1669021473407-34726394271280"}' --accountId dev-1669021948335-14262252549691

near call dev-1669021473407-34726394271280 storage_deposit --accountId dev-1669018198583-29903555965521 --depositYocto 1000000000000000000000000

near call dev-1669021473407-34726394271280 ft_transfer '{"receiver_id": "tungleanh.testnet","amount": "100000000000000000000000", "memo": "None" }' --accountId dev-1669021473407-34726394271280 --depositYocto 1


near call dev-1669021473407-34726394271280 ft_transfer_call '{"receiver_id": "dev-1669021948335-14262252549691", "amount": "10000000", "memo": "None", "msg": "None"}' --accountId dev-1669018198583-29903555965521 --depositYocto 1 --gas=75000000000000

near call dev-1668735602026-81766650624861 unstake_token '{"_amount": "10000000"}' --accountId tungleanh.testnet --depositYocto 1

near view dev-1669021948335-14262252549691 get_staked_amount '{"_advisor_id": "tungleanh.testnet"}'

near view dev-1669021473407-34726394271280 ft_balance_of '{"account_id": "tungleanh.testnet"}'

>>>>>>>>> appp
Version nead signature
app contract: dev-1669022432132-58804567266197 (branch main)
near call dev-1669022432132-58804567266197 new '{"_verified_amount": "1", "_token_address": "dev-1669021473407-34726394271280", "_staking_address": "dev-1669021948335-14262252549691"}' --accountId dev-1669022432132-58804567266197


Version not need signature
app contract: dev-1669349830892-52864076530996 (branch dev)
near call dev-1669349830892-52864076530996 new '{"_verified_amount": "1", "_token_address": "dev-1669021473407-34726394271280", "_staking_address": "dev-1669021948335-14262252549691"}' --accountId dev-1669349830892-52864076530996