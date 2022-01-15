<template>
  <view class="index">
    <button>1111111</button>
    <text class="test"> 11 </text>
    <scroll-view>++++++++</scroll-view>
  </view>
</template>

<script>
import { onMounted, reactive, ref, computed } from 'vue'
import './index.scss'

// import { useStore } from 'vuex'

export default {
  name: 'test',
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
  }
}
</script>

