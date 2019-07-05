<template>
<div>
  <div class="app-download-bar app-topbar" style>
    <a href="http://m.piaoniu.com/appDownload.html?from=mweb">
      <div class="logo"></div>
      <div class="copywrite">
        <p class="top">下载票牛APP</p>
        <p class="bottom">领188元新人礼包</p>
      </div>
      <div class="button">立即下载</div>
    </a>
  </div>
  <!-- <div class="search-header-home light">
    <ul class="scroll-ul">
      <div class="ui-fixed-header full-header">
        <div class="topbar">
          <div class="city-picker">
            北京
            <i class="city-entry-arrow"></i>
          </div>

          <div class="ui-searchbox">
            <div class="ui-inner">
              <input type="text" value class="search-input" placeholder="搜索明星、演出、场馆" />
            </div>
          </div>

          <div class="person-wrap">
            <a href="/user/person.html" class="person-icon"></a>
          </div>
        </div>
      </div>
    </ul>
  </div> -->
<div class="topbar"><div class="city-picker">北京</div><div class="ui-searchbox"><div class="ui-inner"><div class="ui-wrap"><div class="ui-icon icon-search"></div><span class="ui-placeholder">搜索明星、演出、场馆</span></div><form action=""><input type="text" value="" class="search-input"><div class="clear-input" style="display:none;"></div></form></div></div><div class="person-wrap"><a href="/user/person.html" class="person-icon"></a></div></div>
</div>
</template>

<style lang="stylus">
.app-download-bar {
    position: static;
    bottom: 0;
    top 0
    background-color: #000;
    background-color: rgba(0,0,0,.7);
    width: 100%;
    height: 50px;
    z-index: 4;
    display: -ms-inline-flexbox;
    display: inline-flex;
    align-items: center;
}
.app-download-bar>a {
    display: -ms-flexbox;
    display: flex;
    width: 100%;
    -ms-flex-align: center;
    align-items: center;
    margin: auto;
}
.app-download-bar .logo {
    border-radius: 5px;
    width: 34px;
    height: 34px;
    margin-left: 15px;
    background-image: url(../../assets/styles/logo.png);
    background-size: 34px 34px;
}
.app-download-bar .copywrite {
    color: #fff;
    font-size: 14px;
    margin-left: 15px;
    -ms-flex: 1;
    flex: 1;
}
.app-download-bar .copywrite {
    color: #fff;
    font-size: 14px;
    margin-left: 15px;
    -ms-flex: 1;
    flex: 1;
}
.app-download-bar .copywrite .bottom {
    font-size: 14px;
}
.app-download-bar .copywrite p {
    color: #fff;
}
.app-download-bar .button, .app-download-bar .button-open {
    text-align: center;
    font-size: 14px;
    margin-right: 15px;
    height: 30px;
    line-height: 30px;
}
.app-download-bar .button {
    background-color: #ff2661;
    border-radius: 15px;
    color: #fff;
    width: 80px;
}
// .search-header-home, .ui-fixed-header {
//   width: 100%;
//   background: #fff;
//   height: 0.44rem;
//   line-height: 0.44rem;
// }

// .topbar {
//   display: flex;
//   height: 100%;
//   width: 100%;
//   align-items: center;

//   .city-picker {
//     color: #262626;
//     height: 100%;
//     font-weight: 500;
//     font-size: 0.14rem;
//     padding: 0 0.1rem 0 0.1rem;
//   }

//   .ui-searchbox {
//     background: #f5f5f5;
//     height: 80%;
//     border: 1px solid #f5f5f5;
//     border-radius: 0.17rem;
//     overflow: hidden;
//     flex: 2;
//   }

//   .ui-inner {
//     height: 100%;
//     display: flex;
//     align-items: center;

//     .search-input {
//       background: #f5f5f5;
//       border: 0;
//       height: 100%;
//     }
//   }

//   .person-wrap {
//     flex: 1;
//     height: 100%;
//   }
// }

// .city-entry-arrow {
//   margin-right: 0.05rem;
//   width: 0;
//   height: 0;
//   border: 4px solid #b0b0b0;
//   border-left-color: transparent;
//   border-right-color: transparent;
//   border-bottom-color: transparent;
//   display: inline-block;
//   margin-left: 0.04rem;
//   margin-top: 0.05rem;
// }
</style>
