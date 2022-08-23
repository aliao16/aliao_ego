<template>
  <div class="layout">
      <!-- 左侧导航区域 -->
      <MyMenu class="menu" :isCollapse='isCollapse'/>
      <!-- 右侧内容区域 -->
      <Content class="content" :class="{isActive:isCollapse}" @changeCollapse='changeCollapse' :isCollapse='isCollapse'/>
  </div>
</template>

<script>
// 页面分为左边菜单栏和右边内容
import MyMenu from './Mymenu.vue'
import Content from './Content.vue'
export default {
    components:{
        MyMenu,
        Content
    },
    data(){
        return {
            // 默认false
            isCollapse:false,
        }
    },
    methods:{
        changeCollapse(){
            this.isCollapse = !this.isCollapse;
        }
    }
}
</script>

<style lang='less' scoped>
.layout{
    .menu{
        background: #112f50;
        // 左侧固定定位，不需要对layout flex
        position: fixed;
        top:0;
        bottom:0;
    }
    .content{
        margin-left: 200px;
        transition: all 0.3s;
    }
    // 点击折叠后，isCollapse变true,右侧内容区域的margin-left变小
    .isActive{
        margin-left: 64px;
    }
}

</style>