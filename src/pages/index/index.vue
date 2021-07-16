<template>
  <view class="index">
    <view class="index">
    <AtNoticebar marquee>
      欢迎使用 Taro UI Vue
    </AtNoticebar>
    <AtButton
      type="primary"
      :on-click="handleClick"
    >
      AtButton
    </AtButton>
    <AtToast :is-opened="show" :text="msg" :on-close="handleClose"></AtToast>
    <AtTabBar :tab-list="tabList" :current="current" :fixed="fixed" :on-click="handleChange"></AtTabBar>
  </view>
  </view>
</template>

<script>
// 按需引入, 更小的应用体积
import { AtButton, AtToast, AtNoticebar, AtTabBar } from 'taro-ui-vue'
import "taro-ui-vue/dist/style/components/button.scss"
import "taro-ui-vue/dist/style/components/toast.scss"
import "taro-ui-vue/dist/style/components/noticebar.scss"
import "taro-ui-vue/dist/style/components/tab-bar.scss"
import "taro-ui-vue/dist/style/components/icon.scss"
import './index.scss' 
export default {
    components: {
    AtButton,
    AtToast,
    AtNoticebar,
    AtTabBar
  },
  data () {
    return {
      msg: 'Hello world!',
      show: false,
      fixed: true,
      tabList: [
        { title: '待办事项', iconType: 'bullet-list', text: 'new' },
        { title: '拍照', iconType: 'camera' },
        { title: '文件夹', iconType: 'folder', text: '100', max: 99 }
      ],
      current: 0
    }
  },
  methods: {
    handleClick () {
      this.show = true
    },
    handleClose () {
      this.show = false
    },
    handleChange (index) {
      console.log(index)
      this.current = index
    }
  },
}
</script>
