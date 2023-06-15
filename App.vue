<template>
  <div id="app">
    <div class="header">
      <div class="header-top">
        <div class="header-left">
          <p> </p>
        </div>
        <div class="header-title">
          <p style="width: 100%; color: aliceblue; font-size: 20px; margin: 0px;">闰土请您喝猹</p>
        </div>
        <div class="header-right">
          <p> </p>
        </div>
      </div>
      <div class="header-bar">
      <nav>
        <div class="bar-link"><router-link to="/">主页</router-link></div>   |  
        <div class="bar-link"><router-link to="/feed">投喂</router-link></div>   |  
        <div class="bar-link"><router-link to="/shop">商店</router-link> </div> |  
        <div class="bar-link"><router-link to="/about">关于</router-link></div>
      </nav>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<style>
body{
  margin: 0px;
  min-width: 320px;
}
#app {
  min-width: 300px;
  margin: 0px;
  text-align: center;
  color: aliceblue;
}

.header{
  height: 80px;
  background-color: #900b65;

}
.header-top{
  padding: 5px 0 5px 0;

  width: 100%;
  display: flex;
  align-items: center;
  justify-items: center;
}
.header-left
{
  width: 20%;
}
.header-title{
  align-items: center;
  display: flex;
  width: 60%;
  text-align: center;

}
nav {
  display: block;
  width: 100%;
  padding: 5px 0;
}
.bar-link{
  display: inline-block;
  padding: 3px 15px ;
}
.header-right
{
  width: 20%;
  align-items: center;
}
.header-bar{
  display: block;
}

nav a {
  font-weight: bold;
  color: aliceblue;
}

nav a.router-link-exact-active {
  color: aliceblue;
}
</style>
