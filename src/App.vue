<template>
  <div id="app">

    <div class="page-header">
      <img src="../src/assets/citiboard.png" alt="" class="logo">
      <p>
        Agile kanban for citi players ;)
      </p>
    </div>

    <menu-bar></menu-bar>

    <router-view/>
  </div>
</template>

<script>
import MenuBar from '@/components/MenuBar'

export default {
  name: 'app',
  components: {
    'menu-bar': MenuBar
  }
}
</script>

<style>
  .page-header h1 {
    font-weight: 300;
  }
  .logo{
    width: 60%;
  }
</style>
