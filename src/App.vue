<script setup>
import HelloWorld from "./components/HelloWorld.vue";
import Login from "./components/Login.vue";
import Register from "./components/Register.vue";
</script>

<template>
<section class="container">
  <div class="tab">
    <div class="teb_menu">
      <div
        class="teb_menu-item"
        v-for="tab in tabs"
        :key="tab"
        :class="{'teb_menu-item-active': activeTab === tab}"
         @click="activeTab = tab" 
      >
        {{ tab }}
      </div>
    
    </div>
    <div class="tab-content">
      <keep-alive>
        <component :is="activeTab"/>
      </keep-alive>
    </div>
  </div>

</section>  

  <HelloWorld />
  <Login />
  <Register />
</template>

<script>
export default {
  data() {
    return {
      tabs: ["Login", "Register"],
      activeTab: "Login",
    };
  },
};
</script>

<style>
.container{
  margin-top: 40px;
  margin-left: 50px;
}
.tab {
}
.teb_menu {
  display: inline-flex;
}
.teb_menu-item {
  padding: 6px 15px;
  background-color:rgb(221, 218, 218);
  cursor: pointer;
 
}
.teb_menu-item-active {
  color: #fff;
  background-color: rgb(55, 85, 138);
}
input {
  padding: 5px 11px;
  margin-bottom: 11px;
}
</style>