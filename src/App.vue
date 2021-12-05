<template>
  <div id="users">
    <div class="el-tabs el-tabs--top el-tabs--border-card">
      
      <TabsMain :tablist="tablist" />

      
      
      
      
      <div class="el-tabs__content">
        <component v-bind:is="currentTabComponent" class="tab"></component>
      </div>
    </div>
  </div>
</template>

<script>
import TabsMain from './components/TabsMain.vue'
import UserInfo from './components/UserInfo.vue'
import UserTrajectories from './components/UserTrajectories.vue'
import UserReleases from './components/UserReleases.vue'
import UserExpress from './components/UserExpress.vue'

export default {
  name: 'App',
  data(){
    return {
      tablist: [
        { id: 'tab-user-info',          name: 'Информация о пользователе',  isActive: true},
        { id: 'tab-user-trajectories',  name: 'Траектории пользователя',    isActive: false},
        { id: 'tab-user-releases',      name: 'Видеорелизы',                isActive: false},
        { id: 'tab-user-express',       name: 'Экспресс-курсы',             isActive: false},
      ]
    }
  },
  components: {
    TabsMain,
    "tab-user-info": UserInfo,
    "tab-user-trajectories": UserTrajectories,
    "tab-user-releases": UserReleases,
    "tab-user-express": UserExpress

  },
  computed: {
    currentTabComponent: function() {
      let result = null;
      for(let i=0; i < this.tablist.length; i++){
        if(this.tablist[i].isActive){
          result = this.tablist[i].id;
          break;
        }
      }
      return result;
    }
  }
}
</script>

<style>
.el-tabs__nav {
    white-space: nowrap;
    position: relative;
    transition: transform .3s;
    float: left;
    z-index: 2;
}
.el-tabs--border-card > .el-tabs__header {
    background-color: #F5F7FA;
    border-bottom: 1px solid #E4E7ED;
    margin: 0;
}
.el-tabs__nav-wrap {
    overflow: hidden;
    margin-bottom: -1px;
    position: relative;
}
.el-tabs__nav-scroll {
    overflow: hidden;
}
body {
    font-family: "Open Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
    font-size: 13px;
    line-height: 1.61539;
    color: #444;
    background-color: #fff;
}
.el-tabs--border-card > .el-tabs__content {
    padding: 15px;
}
.el-tabs__content {
    overflow: hidden;
    position: relative;
}
</style>

<style scoped>

 .el-tabs--border-card {
    background: #FFFFFF;
    border: 1px solid #DCDFE6;
    box-shadow: 0 2px 4px 0 rgb(0 0 0 / 12%), 0 0 6px 0 rgb(0 0 0 / 4%);
}


</style>
