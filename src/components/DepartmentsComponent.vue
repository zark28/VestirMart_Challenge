<template>
  <nav class="department flex-center-row" :class="{ active: showDepartmentsMenu }">
    <span class="flex-center-row">
      <div class="department-list flex-center-column">
        <h3 @click="handleToggle" class="flex-center-row" :class="{ active: showDepartments }">
          <span class="material-symbols-outlined"> menu </span>
          All Departments
          <span class="material-symbols-outlined arrow"> keyboard_arrow_down </span>
        </h3>
        <ul v-show="showDepartments" class="flex-center-column">
          <li v-for="(item, index) in departments" :key="index" class="flex-center-row">
            <span class="flex-center-row" style="gap: 10px">
              <span class="dot"></span>
              {{ item }}
            </span>
            <span class="material-symbols-outlined arrow"> navigate_next </span>
          </li>
        </ul>
      </div>
      <div class="navlinks flex-center-row">
        <router-link
          class="flex-center-row"
          v-for="(navItem, index) in navItems"
          :key="index"
          :to="navItem.name"
        >
          <span v-show="navItem.icon" class="material-symbols-outlined"> inventory_2 </span>
          {{ navItem.name }}
          <span v-show="navItem.list" class="material-symbols-outlined"> keyboard_arrow_down </span>
        </router-link>
      </div>
    </span>
    <div class="options flex-center-row">
      <div class="flex-center-row">
        $USD
        <span class="material-symbols-outlined"> keyboard_arrow_down </span>
      </div>
      <span class="line"></span>
      <div class="flex-center-row">
        English
        <span class="material-symbols-outlined"> keyboard_arrow_down </span>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'ChallengeDepartmentsComponent',
  props: ['showDepartmentsMenu'],

  data() {
    return {
      showDepartments: false,
      departments: [
        'Smart Phone',
        'Iphone Series 1',
        'Andriod Phone',
        'Smart TV',
        'Smart Light',
        'Smart Mobile',
        'Smart Fan',
        'Smart Camera',
        'Android Phone 01',
        'Iphone Series 1'
      ],
      navItems: [
        { name: 'Home', list: false, icon: false },
        { name: 'Shop', list: true, icon: false },
        { name: 'Featured', list: true, icon: false },
        { name: 'About Us', list: false, icon: false },
        { name: 'Blog', list: false, icon: false },
        { name: 'Promotion', list: false, icon: true }
      ]
    }
  },

  mounted() {},

  methods: {
    handleToggle() {
      this.showDepartments = !this.showDepartments
    }
  }
}
</script>

<style lang="css" scoped>
.department {
  background: var(--pm-dark);
  width: 100%;
  justify-content: space-between;
  padding: 0 200px;
}

.department-list {
  height: 100%;
  position: relative;
  transition: all 0.5s ease;
  padding: 15px 10px;
  background: var(--pm-red);
}
a {
  color: var(--sc-white-dark);
}
.department-list h3 {
  cursor: pointer;
  gap: 10px;
  font-size: 15px;
}
span {
  transition: all 0.2s ease-in-out;
}
h3.active .arrow {
  transition: all 0.2s ease-in-out;
  transform: rotate(180deg);
}

ul {
  position: absolute;
  top: 45px;
  background: var(--pm-blue-black);
  width: 100%;
  gap: 20px;
  padding: 10px 0px;
  list-style: none;
  margin-top: 5px;
  animation: dropdown 0.5s forwards;
  overflow: hidden;
}
li {
  cursor: pointer;
  width: 100%;
  padding: 0 10px;
  justify-content: space-between;
  color: var(--sc-white);
  /* text-align: center; */
  transition: all 0.2s ease-in-out;
}

li .dot {
  width: 5px;
  height: 5px;
  background: var(--sc-white-dark);
  display: inline-block;
  border-radius: 50%;
}
li .arrow {
  font-size: 15px;
}
li:hover {
  color: var(--pm-blue-black);
  background: var(--pm-white);
}
.navlinks {
  gap: 20px;
  margin-left: 40px;
}

.options {
  color: var(--sc-white-dark);
  gap: 10px;
}

.line {
  width: 2px;
  background: var(--sc-white);
  height: 15px;
  margin: 0 10px;
}
.navlinks a:last-of-type span {
  margin-right: 5px;
}
@keyframes dropdown {
  0% {
    height: 0;
  }
  /* 50%{height: 100px;} */
  100% {
    height: 450px;
  }
}
@media screen and (min-width: 1272px) {
  .department {
    padding: 0 200px;
  }
}
@media screen and (max-width: 1271px) {
  .department {
    padding: 0 50px;
  }
}
@media screen and (max-width: 980px) {
  .department {
    background: var(--pm-white);
    flex-direction: column;
    /* background: #000; */
    width: fit-content;
    height: 100dvh;
    position: absolute;
    top: 0;
    left: -400px;
    transition: all 0.3s ease-in-out;
    z-index: 9999;
    padding: 0;
    box-shadow: 8px 4px 20px 20px #0000001f;
  }

  .department.active {
    transition: all 0.3s ease-in-out;
    left: 0;
  }
  .department > span,
  .navlinks {
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
  }

  .navlinks {
    width: 100%;
    margin: 0;
    padding: 10px;
  }
  .navlinks a {
    width: 100%;
    align-items: flex-start;
    justify-content: space-between;
    gap: 10px;
  }
  .navlinks a:last-of-type {
    flex-direction: row-reverse;
  }

  .navlinks a:last-of-type span {
    margin-right: 0;
  }
}
</style>
