<template>
    <div class="home">
        <div class="sidebar-menu-con">
            <SideBarMenu :menuList="menuList" :menuTheme="menuTheme" :activeMenuName="activeMenuName" :openNames="openNames">
                <div slot="top" class="logo-con">
                    <img src="../images/logo.jpg" key="max-logo" />
                </div>
            </SideBarMenu>
        </div>
  </div>
</template>

<script>
import SideBarMenu from './SideBarMenu.vue'

export default {
  name: 'Home',
  components: {
      SideBarMenu
  },
  data () {
    return {

    }
  },
  computed: {
      menuTheme() {
          return 'dark'
      },
      activeMenuName() {
          return 'article'
      },
      openNames() {
          return ['content']
      },
      menuList() {
          return [{
              icon: 'ios-paper',
              name: 'content', 
              title: '内容管理',
              children: [{
                    icon: '',
                    name: 'article', 
                    title: '文章管理'
              },{
                    icon: '',
                    name: 'comment', 
                    title: '评论管理'
              },{
                    icon: '',
                    name: 'report', 
                    title: '举报管理'
              }]
          }, {
              icon: 'ios-people',
              name: 'user', 
              title: '用户管理',
              children: [{
                    icon: '',
                    name: 'newUser', 
                    title: '新增用户'
              },{
                    icon: '',
                    name: 'activityUser', 
                    title: '活跃用户'
              }]
          }, {
              icon: 'stats-bars',
              name: 'stat', 
              title: '统计分析',
              children: [{
                    icon: '',
                    name: 'newAndStart', 
                    title: '新增和启动'
              },{
                    icon: '',
                    name: 'activity', 
                    title: '活跃分析'
              },{
                    icon: '',
                    name: 'timeline',
                    title: '时段分析'
              }]
          }]
      }
  }
}
</script>

<style scoped>
.home {
    position: absolute;
    width: 100%;
    height: 100%;
}
.logo-con{
    margin-top: -250px;
    padding: 8px;
    text-align: center;
    height: 44px;
    width: auto;
}
.sidebar-menu-con {
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 21;
    transition: width .3s;
}
</style>
