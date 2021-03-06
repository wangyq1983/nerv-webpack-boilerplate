Nervjs-webpack-boilerplate
---

A simple Webpack boilerplate with Nervjs.

## Features

* 🤖[Nerv](https://github.com/NervJS/nerv) inside
* Inline [Polyfill](https://github.com/o2team/es5-polyfill) for IE8 support !
* [Webpack](https://github.com/webpack/webpack) based
* [Typescript](https://github.com/Microsoft/TypeScript) support
* JSX/TSX support
* SCSS support
* [Babel](https://github.com/babel/babel) with [@babel/preset-env](https://github.com/babel/babel/tree/master/packages/babel-preset-env)
* Precommit hooks:
    * StyleLint with [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard) rules
    * ESLint with [eslint-config-standard](https://github.com/standard/eslint-config-standard) rules
    * TSLint with [tslint-config-standard](https://github.com/blakeembrey/tslint-config-standard) rules
    * Automatically fix code style using [Prettier](https://github.com/prettier/prettier)

## Usage

* Install:
    `npm install`

* Run dev server:
    `npm run dev`

* Build:
    `npm run build`

* Run in IE 8
    `npm run deploy`
    
    
    ============
    
    使用了axios，发现ie8不支持， 
    npm install --save babel-polyfill
    import 'babel-polyfill';


打包时自动去除console.log 

webpack.config.js

const uglifyJSPlugin = new UglifyJSPlugin({
  uglifyOptions: {
    ie8: true,
    keep_fnames: true,
    compress: {
      warnings: false,
      drop_console: true,
      pure_funcs: ['console.log']
    }
  }
});

optimization: {
    minimizer: [uglifyJSPlugin]
  }
