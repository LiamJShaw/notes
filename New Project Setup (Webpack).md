# New Project Setup
Basic setup of a project that uses:  
- NPM
- Webpack
- Prettier
- ESLint
- Jest  

## Create and clone git repo

## File Structure

`mkdir src dist`  
`mkdir src/styles src/modules src/fonts`  
`touch dist/index.html`  
`touch src/index.js src/styles/styles.css`  

## NPM

`npm init -y`  

(Can set `private: true` here)  

## Webpack

`npm install webpack webpack-cli --save-dev`  

`touch webpack.config.js`  


### Basic Webpack config:

    const path = require('path');

    module.exports = {
    entry: './src/index.js',
    output: {
        filename: 'main.js',
        path: path.resolve(__dirname, 'dist'),
      },
    };

### Set up `npm run build`

Add the following to `package.json`:  

    "scripts": {
        "build": "webpack"
    },

### Set up loading CSS, images, and fonts
`npm install --save-dev style-loader css-loader`  

Add the following to `webpack.config.js`:  

    module: {
        rules: [
            {
                test: /\.css$/i,
                use: ['style-loader', 'css-loader'],
            },
            {
                test: /\.(png|svg|jpg|jpeg|gif)$/i,
                type: 'asset/resource',
            },
            {
                test: /\.(woff|woff2|eot|ttf|otf)$/i,
                type: 'asset/resource',
            },
        ],
    },

## ESLint

Install: `npm install eslint --save-dev`  

Init config: `npm init @eslint/config`  

Run: `npx eslint file`  

VSCode extension?  

## Prettier

Install: `npm install --save-dev --save-exact prettier`  

Init config: `echo {}> .prettierrc.json`  

Stop Prettier formatting certain files:  
`touch .prettierignore`  

Base it on your .gitignore  

Run: `npx prettier --write`

Make Prettier and ESLint work nicely together: https://github.com/prettier/eslint-config-prettier#installation