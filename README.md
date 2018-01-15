# multipage-helper.js
# 多页面vue配置
#  ./webpack.base.conf.js
  entry: mulitipage.getEntries()
#   webpack.dev.conf.js
    // new HtmlWebpackPlugin({
    //   filename: 'index.html',
    //   template: 'index.html',
    //   inject: true
    // }),
    底部改为
    devWebpackConfig.plugins.push(...mulitipage.getDevHtmlWebpackPluginList())
#  ./webpack.prod.conf.js
   去掉
    // new HtmlWebpackPlugin({
    //   filename: process.env.NODE_ENV === 'testing'
    //     ? 'index.html'
    //     : config.build.index,
    //   template: 'index.html',
    //   inject: true,
    //   minify: {
    //     removeComments: true,
    //     collapseWhitespace: true,
    //     removeAttributeQuotes: true
    //     // more options:
    //     // https://github.com/kangax/html-minifier#options-quick-reference
    //   },
    //   // necessary to consistently work with multiple chunks via CommonsChunkPlugin
    //   chunksSortMode: 'dependency'
    // }),
    改为
    webpackConfig.plugins.push(...mulitipage.getProdHtmlWebpackPluginList())
