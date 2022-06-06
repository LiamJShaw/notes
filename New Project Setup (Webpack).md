# New Project Setup
## NPM / Webpack / Prettier / ESLint / Jest

1. ### Create and clone git repo

2. ### File Structure
mkdir src dist
mkdir src/styles src/modules
touch dist/index.html
touch src/index.js src/styles/styles.css

### NPM
npm init -y

(Can set "private: true" here)

### Webpack
npm install webpack webpack-cli --save-dev

touch webpack.config.js

#### Basic Webpack config:
`const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist'),
  },
};`