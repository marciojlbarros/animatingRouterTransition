<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <div class="content">
    <router-link to="/">Home</router-link>
    <router-link to="/guide">Guide</router-link>
      <router-view v-slot="{ Component, route }">
        <transition 
        :enter-active-class="route.meta.enterClass"
        :leave-active-class="route.meta.leaveClass"
        mode="out-in">
          <component :is="Component" />
        </transition>
      </router-view>
  </div>
</template>

<style scoped>
.content {
  text-align: left;
  width: 40%;
  min-width: 400px;
  margin: 50px;
}

a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  margin-right: 1em;
}

a:hover,
a.router-link-active {
  border-bottom: 2px solid #3498db;
}

.fade-enter-from, .fade-leave-to {
  opacity: 0;
}

.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s ease-out;
}

</style>
