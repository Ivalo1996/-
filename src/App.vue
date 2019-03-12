<template>
  <div id="app">
    <div id="icon" >后台监控</div>
    <div id="header"></div>
    <div>
      <div id="wrap">
        <iframe src="http://10.100.156.233:5601/app/kibana#/dashboard/AWiiG2dXVZzDKbILRHi_?_g=(refreshInterval:(display:Off,pause:!f,value:0),time:(from:now%2Fd,mode:quick,to:now%2Fd))&_a=(description:'',filters:!(),options:(darkTheme:!f),panels:!((col:1,id:AWiiGB9bVZzDKbILRHip,panelIndex:1,row:1,size_x:6,size_y:3,type:visualization),(col:7,id:AWiiGP1sVZzDKbILRHiq,panelIndex:2,row:1,size_x:6,size_y:3,type:visualization)),query:(match_all:()),timeRestore:!f,title:nginx,uiState:(),viewMode:view)" id="mobsf" scrolling="no" frameborder="0" ></iframe>
      </div>
    </div>
    <div id="slider">
      <el-menu
        default-active="2"
        class="el-menu-vertical-demo">
      <el-submenu index="1">
        <template slot="title">
          <i class="el-icon-menu"></i>
          <span>pavo</span>
        </template>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-submenu>
        <el-submenu index="2">
          <template slot="title">
            <i class="el-icon-menu"></i>
            <span>mq</span>
          </template>
          <el-menu-item index="2-1">选项1</el-menu-item>
          <el-menu-item index="2-2">选项2</el-menu-item>
          <el-menu-item index="2-3">选项3</el-menu-item>
        </el-submenu>
        <el-submenu index="3">
          <template slot="title">
            <i class="el-icon-menu"></i>
            <span>kafka</span>
          </template>
          <el-menu-item index="3-1">选项1</el-menu-item>
          <el-menu-item index="3-2">选项2</el-menu-item>
          <el-menu-item index="3-3">选项3</el-menu-item>
        </el-submenu>
        <el-submenu index="4">
          <template slot="title">
            <i class="el-icon-menu"></i>
            <span>短链</span>
          </template>
          <el-menu-item index="4-1">选项1</el-menu-item>
          <el-menu-item index="4-2">选项2</el-menu-item>
          <el-menu-item index="4-3">选项3</el-menu-item>
        </el-submenu>
    </el-menu>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {}
  },
  mounted () {
    function changeMobsfIframe () {
      const mobsf = document.getElementById('mobsf');
      const deviceWidth = document.body.clientWidth;
      const deviceHeight = document.body.clientHeight;
      const header=document.getElementById('header');
      const slider=document.getElementById('slider');
      header.style.width='87%';
      header.style.height='10%';
      slider.style.width='13%';
      slider.style.height='90%';
    }

    changeMobsfIframe()

    window.onresize = function () {
      changeMobsfIframe()
    }
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  },

  name: 'App'
};

</script>

<style>
*{
  margin:0;
padding:0;
}
body,html{
  width:100%;
  height:100%;
  background:#e5e9f2;
}
#icon{
  position:absolute;
  z-index:999;
  width:13%;
  height:10%;
  background:#324057;
  text-align:center;
  font-size:2em;
  font-weight:600;
  font-family: "Nunito";
  line-height:300%;
  color:white;
}
#header{
  position:absolute;
  top:0;
  left:13%;
  z-index:998;
  background:#324057;
  text-align:center;
  font-size:30px;
  font-weight:600;
  font-family: "Nunito";
  color:white;
  line-height:300%;
}
#slider{
  position:absolute;
  top:10%;
  left:0;
  background: white;
}
#wrap{
  position:absolute;
  top:15%;
  bottom:3%;
  left:17%;
  right:6%;
  width:79%;
  height:82%;
  background:white;
  border:2px solid #e5e9f2;
  border-radius:10px;
}
iframe{
  position:relative;
  width:100%;
  height:100%;
}
</style>
