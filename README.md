## Intro

Welcome to starknet_dapp, a sample Starknet application built with Next.js 14 and Material UI. It lets users seamlessly transfer funds between wallet addresses, featuring an intuitive wallet-connection modal powered by starknetkit and real-time wallet state management via starknet-react hooks. Check out the full code on GitHub!

## Update node version (optional)

To run the program you first need to install the correct version of node. Please skip this step if running `node -v` in the terminal shows the default version 18 or later.

1. Install node (If it's not installed):

    ```shell
    brew install node
    ```

2. Install nvm (If it's not installed):

-   Create .zshrc file for **Mac only** (If it doesn't exist):
    ```shell
    touch ~/.zshrc
    ```
-   Install nvm:
    ```shell
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
    ```

3. Use node 16.17.0 as default:

-   Install node 16.17.0 (Check `nvm ls` for installed versions):

    ```shell
    nvm install 16.17.0
    ```

-   Set node 16.17.0 as the default:
    ```shell
    nvm alias default 16.17.0
    ```

## Run frontend

1. Run `yarn` to install all dependencies
2. Run `yarn dev` to start the frontend
3. Open http://localhost:3000 in your browser

## Deploy smart contract

1. Install `Starkli` and `Scarb` using the official [starknet instructions](https://docs.starknet.io/quick-start/environment-setup/)
2. Change directory using `cd contracts`
3. Build your contract `scarb build`
4. Declare smart contract on Starknet:
    ```shell
     starkli declare --account ~/.starkli-wallets/deployer/account.json --keystore ~/.starkli-wallets/deployer/keystore.json --network sepolia --rpc <rpc url> --compiler-version 2.7.1 target/dev/erc20_new_MyToken.contract_class.json
    ```
5. Deploy smart contract:
    ```shell
    starkli deploy --account ~/.starkli-wallets/deployer/account.json --keystore ~/.starkli-wallets/deployer/keystore.json --network sepolia --rpc <rpc url> <contact hash/first constructor param - received from previous step> <remaining contructor inputs - optional>
    ```
