<template>
  <view>
    <view class="indexBac"> </view>
    <view class="index">
      <view :style="statusHei"> </view>
      <view class="content">
        <view class="sea_search" @click="toSearch()">
          <image class="sea_search_image" src="./search.png"> </image>

          <input
            placeholder="请输入文本"
            :v-bind="searchData"
            @input="toSearch"
            class="sea_search_text"
          />
        </view>

        <image class="new_content_img"> </image>
        <view class="new_content_txt">12</view>

        <view class="main_table" >

          <view class="flex_h" > 

            <view class="flex_v "> <image class="tab_img" @click="report_event" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>
            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>
            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>
            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>

          </view>

          <view class="flex_b_1"> </view>

          <view class="flex_h" > 

            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>
            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>
            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>
            <view class="flex_v "> <image class="tab_img" src = "./line1.png"> </image> <view class="tab_txt"> 事件上报 </view> </view>

          </view>

          <view class="flex_b_2"> </view>



        </view>

        <view></view>
      </view>
    </view>
  </view>
</template>
<script >
import Taro, { eventCenter, getCurrentInstance } from "@tarojs/taro";

var unique_supcon_id = 1;
export default {
  name: "Index",

  components: {},

  data() {
    return {};
  },

  methods: {
    // 点击返回一般处理
    invokeClickBack() {
      Taro.navigateBack({
        delta: 1,
      });
    },

    // todo 点击事件一般处理
    invokeClick(id) {
      processClick(this, id);
    },

    // todo 获取v-for uuid
    getUUIDforVfor(item) {
      if (!item) {
        return "";
      }
      if (typeof item == "string") {
        return item;
      }
      if (!item.supcon_uuid_index) {
        item.supcon_uuid_index = unique_supcon_id++;
      }
      return item.supcon_uuid_index;
    },

    isEmpty(item) {
      if (!item) {
        return true;
      }
      if (item instanceof Array) {
        return item.length == 0;
      }

      if (item instanceof Object) {
        return "{}" == JSON.stringify(item);
      }
      return false;
    },

    report_event(){
        // Taro.navigateTo({
        //   ""
        // })

    },



  },

  mounted() {
    // let naviData = navigateDataGet(pageDate.url);
    // pageCache(pageDate.url, this);
    // processLinkData(this, naviData);
    // processInitData(this, naviData);
    // processApi(this);
  },

  onShow() {},

  computed: {
    statusHei() {
      if (Taro.getEnv() == Taro.ENV_TYPE.WEAPP) {
        let systemInfo = wx.getSystemInfoSync();
        let hei = systemInfo.statusBarHeight;
        return {
          display: "block",
          width: "100%",
          height: hei + "px",
        };
      }
      return {};
    },

    indexHei() {
      if (Taro.getEnv() == Taro.ENV_TYPE.WEAPP) {
        let systemInfo = wx.getSystemInfoSync();
        let hei = systemInfo.statusBarHeight;
        return {
          height: hei + pageDate.pageContentHei + "px",
        };
      }
      return {
        height: pageDate.pageContentHei + "px",
      };
    },

    canGoBack() {
      let tabList = commonData.tabList;
      if (tabList) {
        for (let item of tabList) {
          if (item == pageDate.url) {
            return false;
          }
        }
      }

      let pages = Taro.getCurrentPages();
      if (pages && pages.length <= 1) {
        return false;
      }

      return true;
    },
  },

  watch: {},

  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
@import "./sy.scss";

.index {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  position: absolute;
  width: 100%;
  min-height: 100%;
}

.content {
  position: relative;
}

.indexBac {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  position: fixed;
  background-color: #E5E5E5;
  width: 100%;
  height: 100%;
}
</style>