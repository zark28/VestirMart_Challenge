<template>
  <div class="page flex-center-column">
    <header class="">
      <TopheaderComponent />
      <NavbarComponent :handleShowDepartment="handleShowDepartment" />
      <DepartmentsComponent :showDepartmentsMenu="showDepartmentsMenu" />
    </header>
    <RouterView />
  </div>
</template>

<script>
import DepartmentsComponent from './components/DepartmentsComponent.vue'
import NavbarComponent from './components/NavbarComponent.vue'
import TopheaderComponent from './components/TopheaderComponent.vue'
export default {
  components: { NavbarComponent, TopheaderComponent, DepartmentsComponent },
  name: 'ChallengeApp',

  data() {
    return {
      showDepartmentsMenu: false
    }
  },

  mounted() {},

  methods: {
    handleShowDepartment() {
      this.showDepartmentsMenu = !this.showDepartmentsMenu
    }
  }
}
</script>

<style lang="css" scoped>
.page {
  width: 100vw;
  /* background: #000; */
  /* background: var(--pm-white-dark); */
}
header {
  background-color: var(--pm-blue-black);
  width: 100%;
}
/* @media screen and (min-width:1272px) {
    .search-container{
    padding: 0 200px;
}
  } */
</style>
