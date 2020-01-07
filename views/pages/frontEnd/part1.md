### part1

```javascript
module.exports = {
  lintOnSave: true,
  devServer: {
    proxy: {
      "/api": {
        target: "http://10.0.21.125:7000",
        changeOrigin: true,
        ws: false
      }
    }
  }
}
```