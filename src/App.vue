<template>
  <!-- <div id="app">
    <router-view />
  </div> -->
  <div class="layout" id="ido">
    <Layout>
      <Sider
        hide-trigger
        collapsible
        :collapsed-width="78"
        ref="side1"
        v-model="isCollapsed">
        <h1 class="logo">
          <img :src="logo" alt="logo" />
          <img
            :src="IDO"
            class="ido-logo"
            alt="IDO" />
        </h1>
        <Menu
          active-name="1-1"
          theme="dark"
          width="auto"
          :class="menuitemClasses">
          <MenuItem name="1-1">
            <Icon type="ios-navigate"></Icon>
            <span>项目管理</span>
          </MenuItem>
          <MenuItem name="1-2">
            <Icon type="ios-search"></Icon>
            <span>Option 2</span>
          </MenuItem>
          <MenuItem name="1-3">
            <Icon type="ios-settings"></Icon>
            <span>Option 3</span>
          </MenuItem>
        </Menu>
        </h1>
      </Sider>
      <Layout>
        <Header :style="{padding: 0}" class="layout-header-bar">
          <Icon
            :class="rotateIcon"
            :style="{margin: '0 20px'}"
            type="md-menu"
            size="24"
            @click.native="collapsedSider" />
          IDO海上风机一体化设计平台
        </Header>
        <Content :style="{margin: '20px', background: '#fff', minHeight: '260px'}">
          Content
        </Content>
      </Layout>
    </Layout>
  </div>
</template>

<script>
import { Layout, Sider, Menu, MenuItem, Header, Icon, Content } from 'iview'
import logo from '@/assets/logo.png'
import IDO from '@/assets/IDO.png'
export default {
  name: 'App',
  components: {
    Layout,
    Sider,
    Menu,
    MenuItem,
    Header,
    Icon,
    Content
  },
  data () {
    return {
      isCollapsed: false,
      logo: logo,
      IDO: IDO
    }
  },
  computed: {
    rotateIcon () {
      return [
        'menu-icon',
        this.isCollapsed ? 'rotate-icon' : ''
      ]
    },
    menuitemClasses () {
      return [
        'menu-item',
        this.isCollapsed ? 'collapsed-menu' : ''
      ]
    }
  },
  methods: {
    collapsedSider () {
      this.$refs.side1.toggleCollapse()
    }
  }
}
</script>

<style lang="less">
html, body {
  height: 100%;
}
.ivu-layout {
  height: 100%;
}
#ido .ivu-layout-sider {
  background: url('./assets/ocean.jpg') no-repeat;
  background-size: cover;
}
#ido .ivu-menu-dark {
  background: rgba(45, 101, 146, 0.54);
}
#ido .ivu-menu-item-active.ivu-menu-item-selected {
  background: rgba(45, 101, 146, 0.54);
  color: #fff;
  font-weight: bold;
}
#ido .ivu-menu-item:hover {
  background: rgba(45, 101, 146, 0.74);
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: 100%;
}
</style>
<style scoped lang="less">
.layout{
  position: relative;
  overflow: hidden;
  height: 100%;
}
.logo {
  height: 60px;
  // background: #5b6270;
  text-align: center;
  padding-top: 10px;

  img {
    height: 32px;
  }

  .ido-logo {
    height: 40px;
  }
}
.layout-header-bar{
    background: #fff;
    box-shadow: 0 1px 1px rgba(0,0,0,.1);
}
.layout-logo-left{
    width: 90%;
    height: 30px;
    background: #5b6270;
    border-radius: 3px;
    margin: 15px auto;
}
.menu-icon{
    transition: all .3s;
}
.rotate-icon{
    transform: rotate(-90deg);
}
.menu-item span{
    display: inline-block;
    overflow: hidden;
    width: 69px;
    text-overflow: ellipsis;
    white-space: nowrap;
    vertical-align: bottom;
    transition: width .2s ease .2s;
}
.menu-item i{
    transform: translateX(0px);
    transition: font-size .2s ease, transform .2s ease;
    vertical-align: middle;
    font-size: 16px;
}
.collapsed-menu span{
    width: 0px;
    transition: width .2s ease;
}
.collapsed-menu i{
    transform: translateX(5px);
    transition: font-size .2s ease .2s, transform .2s ease .2s;
    vertical-align: middle;
    font-size: 22px;
}
</style>
