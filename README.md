# Ethereum Block Explorer

Welcome to the Ethereum Block Explorer project! This project is a simple block explorer for the Ethereum blockchain built using React and the Alchemy SDK. It allows users to view the latest block number and details about blocks and transactions on the Ethereum mainnet.

This is the project for the 3rd week of the Ethereum Developer BootCamp at Alchemy University.

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Prerequisites](#prerequisites)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Project Structure](#project-structure)
7. [Configuration](#configuration)
8. [Contributing](#contributing)
9. [License](#license)

## Introduction

Block explorers give us the ability to view various information about the blockchain, including data about:
- The blockchain network itself
- Blocks in the blockchain
- Transactions in a block
- Accounts

This project aims to create a simple block explorer similar to [Etherscan](https://etherscan.io/), allowing users to query and display information about Ethereum blocks and transactions.

## Features

- Display the latest Ethereum block number.
- Retrieve and display details about specific blocks.
- Retrieve and display transactions within a block.
- Provide detailed information about individual transactions.

## Prerequisites

Before you begin, ensure you have met the following requirements:
- You have installed Node.js and npm.
- You have an Alchemy account and an API key for the Ethereum mainnet.

## Installation

To install the project, follow these steps:

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/ethereum-block-explorer.git
    ```

2. Navigate to the project directory:
    ```sh
    cd ethereum-block-explorer
    ```

3. Install the project dependencies:
    ```sh
    npm install
    ```

4. Create a `.env` file in the root directory and add your Alchemy API key:
    ```sh
    REACT_APP_ALCHEMY_API_KEY=your-alchemy-api-key
    ```

## Usage

To run the project in development mode, use the following command:
```sh
npm start

This will start the development server and open the application in your default web browser at http://localhost:3000.

Example Interactions
View the latest block number on the homepage.
Enter a block number to retrieve details about that block.
View a list of transactions within a specific block.
Click on a transaction to see detailed information about it.
Project Structure
The project structure is as follows:

java
Copy code
ethereum-block-explorer/
├── node_modules/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── App.css
│   ├── App.js
│   ├── index.js
│   ├── setupProxy.js
│   └── ...
├── .env
├── .gitignore
├── package.json
├── README.md
└── ...
public/: Contains the public assets for the project.
src/: Contains the source code for the React application.
.env: Contains the environment variables for the project.
setupProxy.js: Configures a proxy to handle CORS issues during development.
Configuration
Environment Variables
The project uses environment variables to store sensitive information. Create a .env file in the root directory and add the following line:

sh
Copy code
REACT_APP_ALCHEMY_API_KEY=your-alchemy-api-key
Replace your-alchemy-api-key with your actual Alchemy API key.

Proxy Setup
To handle CORS issues, a proxy is set up using http-proxy-middleware. The proxy configuration is in src/setupProxy.js:

javascript
Copy code
const { createProxyMiddleware } = require('http-proxy-middleware');

module.exports = function(app) {
  app.use(
    '/api',
    createProxyMiddleware({
      target: 'https://eth-mainnet.g.alchemy.com',
      changeOrigin: true,
      pathRewrite: {
        '^/api': '',
      },
    })
  );
};
This project is part of the third week of the Ethereum Developer BootCamp at Alchemy University.
