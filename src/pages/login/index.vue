<template>
  <view class="index">
    <view class="index_img_1"></view>

    <image src="./icon_mark_mini.png" class="index_img" />

    <image src="./zhyj.png" class="index_zhyj" />

    <view class="index_img_2"></view>

    <view class="index_content">
      <view class="index_user_part_1"></view>

      <view class="index_user_part">
        <image src="./user_au.png" class="index_user_part_au"> </image>
        <input class="index_user_part_input" placeholder="请输入用户名" />
      </view>

      <view class="index_user_part_line"></view>

      <view class="index_user_part_2"></view>

      <view class="index_user_part">
        <image src="./user_au.png" class="index_user_part_au"> </image>
        <input
          :type="isShowPass ? 'text' : 'password'"
          class="index_user_part_input"
          placeholder="请输入密码"
        />
        <image
          src="./password.png"
          v-on:click="showPassWord"
          class="index_user_part_pass_word"
        >
        </image>
      </view>
      <view class="index_user_part_line"></view>

      <view class="index_user_part_3"></view>

      <view class="index_user_part_dl"> 登陆 </view>

      <view class="index_user_thrid">
        <view class="index_user_thrid_split"> </view>
        <view class="index_user_thrid_c"> 其他方式登录</view>
        <view class="index_user_thrid_split"> </view>
      </view>

      <view class="index_user_thrid_direct">
        <view class="flex_grow1"></view>

        <image class="index_user_thrid_wx" src="./wx.png"> </image>

        <image class="index_user_thrid_dd" src="./dd.png"> </image>

        <view class="flex_grow1"> </view>
      </view>
    </view>

    <view class="flex_grow1"> </view>

    <view class="index_f_pass">忘记密码？</view>

    <view class="flex_grow1"> </view>
  </view>
</template>

<script>

import { onMounted, reactive, ref, computed } from "vue";

export default {
  name: "test",
  data() {
    return {
      isShowPass: false,
    };
  },
  methods: {
    showPassWord() {
      this.isShowPass = !this.isShowPass;
      console.log(":::::::::::::::::::: show pass word " + this.isShowPass);
    },
  },
  setup() {
    // const store = useStore()
    // const count = computed(() => store.state.userInfo.count)
    // const res = ref([])
    // const msg = ref('111')
    // const getRes = async () => {
    //   const result = await test()
    //   res.value = result
    // }
    // getRes()
    // return { res, msg }
  },
};
</script>

<style lang="scss" scoped>

@import "./index.scss";
</style>