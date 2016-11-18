## Android问题
- WebView读入的网页，CSS的margin失效  
    因为我以前用 setLayoutAlgorithm 设定了 SINGLE_COLUMN。  
    myWebViewObj = (WebView) findViewById(R.id.ui_webview);  
    myWebViewObj .getSettings().setLayoutAlgorithm(WebSettings.LayoutAlgorithm.SINGLE_COLUMN);  设定了之后，可能很多CSS就乱掉了，不仅仅magin的左右，连height都不准了。  
还没有研究SINGLE_COLUMN是怎么回事，至少去掉这个设定，我的问题就解决了。  
**Android 4.4修复了这个问题， 4.4以前调用自适应那个属性--WebSettings.LayoutAlgorithm.SINGLE_COLUMN会导致css乱掉**