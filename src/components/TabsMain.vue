<template>
    <div class="el-tabs__header is-top">
        <div class="el-tabs__nav-wrap is-top">
            <div class="el-tabs__nav-scroll">
                <div class="el-tabs__nav">
                    <div class="el-tabs__item"
                        v-for="(tab, index) in tablist" :key="index"               
                        :class="{ 'is-active': tab.isActive }"
                        :id="tab.id"
                        @click="checkTab(tab)"
                    >{{ tab.name }}</div>  
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: ['tablist'],
    methods:{
        checkTab(tab){
            this.tablist.forEach(el => {
                el.isActive = false;
            });
            tab.isActive = true;

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
.el-tabs__item {
    padding: 0 20px;
    height: 40px;
    box-sizing: border-box;
    line-height: 40px;
    display: inline-block;
    list-style: none;
    font-size: 14px;
    font-weight: 500;
    color: #303133;
    position: relative;
}
.el-tabs--border-card > .el-tabs__header {
    background-color: #F5F7FA;
    border-bottom: 1px solid #E4E7ED;
    margin: 0;
}
.el-tabs__header {
    padding: 0;
    position: relative;
    margin: 0 0 15px;
}
.el-tabs__nav-wrap {
    overflow: hidden;
    margin-bottom: -1px;
    position: relative;
}
.el-tabs__nav-scroll {
    overflow: hidden;
}
.el-tabs--border-card > .el-tabs__header .el-tabs__item:first-child {
    margin-left: -1px;
}
.el-tabs--border-card > .el-tabs__header .el-tabs__item {
    transition: all 0.3s cubic-bezier(0.645, 0.045, 0.355, 1);
    border: 1px solid transparent;
    margin-top: -1px;
    color: #909399;
}
.el-tabs--border-card > .el-tabs__header .el-tabs__item.is-active {
    color: teal;
    background-color: #FFFFFF;
    border-right-color: #DCDFE6;
    border-left-color: #DCDFE6;
}
</style>
