<template>
  <div class="app-main-layout">
    
  <navbar @click="isOpen = !isOpen" />

  <sidebar v-model="isOpen" />
  
    <main class="app-content" :class="{full : !isOpen}">
      <div class="app-page">
        <router-view />
      </div>
    </main>

    <div class="fixed-action-btn">
      <a class="btn-floating btn-large blue" href="#">
        <i class="large material-icons">add</i>
      </a>
    </div>
  </div>
</template>

<script>
  import navbar from '@/components/app/Navbar'
  import sidebar from '@/components/app/Sidebar'

  export default {
    data () {
      return {
        isOpen: true
      }
    },
    name: 'main-layout',
    components: {
      navbar,
      sidebar
    }
  } 
</script>