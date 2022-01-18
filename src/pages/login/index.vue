<template>
  <view class="index">
    <image src="./icon_mark_mini.png" class="index_img" />

    <view class="index_content">
      <view class="index_user_part">
        <image src="./user_au.png" class="index_user_part_au"> </image>
        <input class="index_user_part_input" placeholder="请输入用户名" />
      </view>
      <view class="index_user_part_line"></view>

      <view class="index_user_part">
        <image src="./user_au.png" class="index_user_part_au"> </image>
        <input class="index_user_part_input" placeholder="请输入用户名" />
      </view>
      <view class="index_user_part_line"></view>


       <view class="index_user_part_dl">  登陆 </view>
  
    </view>

    <text class="test"> 11 </text>
    <scroll-view>++++++++</scroll-view>
  </view>
</template>

<script>
import { onMounted, reactive, ref, computed } from "vue";

import "./index.scss";

// import { useStore } from 'vuex'

export default {
  name: "test",
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

