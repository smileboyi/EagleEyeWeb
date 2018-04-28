<template>
  <div id="app" class="grail w100">
    <router-view/>
  </div>
</template>

<script>
import home from '@/pages/home'


export default {
  name: 'App',
  components: {
    home
  }
}
</script>

<style>
  body{
    max-width: 1900px;
    min-width: 900px;
  }
</style>
