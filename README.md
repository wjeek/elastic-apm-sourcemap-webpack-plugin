# ElasticAPMSourceMapPlugin

## Example

An example of `webpack.config.js`:

```js
const ElasticAPMSourceMapPlugin = require('elastic-apm-sourcemap-webpack-plugin');
const path = require('path');
const PUBLIC_PATH = 'https://path/to/assets';

const webpackConfig = {
  mode: 'production',
  entry: path.resolve(__dirname, './entry.js'),
  publicPath: PUBLIC_PATH,
  output: {
    path: 'build',
    filename: 'index-[hash].js'
  },
  plugins: [
    new ElasticAPMSourceMapPlugin({
      serviceName: 'SERVICE_NAME',
      serviceVersion: 'SERVICE_VERSION',
      serverURL: 'http://127.0.0.1:8200/assets/v1/sourcemaps',
      publicPath: PUBLIC_PATH,
      secret: 'SECRET',
      logLevel: 'debug'
    })
  ]
};
```
