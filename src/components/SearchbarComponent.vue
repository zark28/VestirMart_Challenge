<template>
  <div class="flex-center-row search-container">
    <div class="categories flex-center-column">
      <h3 @click="handleToggle" class="flex-center-row" :class="{ active: showCategories }">
        All Categories
        <span class="material-symbols-outlined"> keyboard_arrow_down </span>
      </h3>
      <ul v-show="showCategories" class="flex-center-column">
        <li>category1</li>
        <li>category2</li>
        <li>category3</li>
        <li>category4</li>
        <li>category5</li>
        <li>category6</li>
        <li>category7</li>
        <li>category8</li>
      </ul>
    </div>
    <div class="search-bar flex-center-row">
      <input
        type="search"
        name="searchbar"
        id="searchbar"
        placeholder="Search products here ......."
        class="desktop-nav"
      />
      <input
        type="search"
        name="searchbar"
        id="searchbar"
        placeholder="Search here ..."
        class="mini-nav"
      />
      <span class="material-symbols-outlined flex-center-row"> search </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChallengeSearchbarComponent',

  data() {
    return {
      showCategories: false
    }
  },

  mounted() {},

  methods: {
    handleToggle() {
      this.showCategories = !this.showCategories
    }
  }
}
</script>

<style lang="css" scoped>
.search-container {
  width: 600px;
  height: 40px;
  background: #000;
  padding: auto 200px;
  margin: 20px 0;
}
.mini-nav {
  display: none;
}

.categories {
  height: 100%;
  width: 30%;
  position: relative;
  transition: all 0.5s ease;
  padding: 0 10px;
  border-top-left-radius: 5px;
  border-bottom-left-radius: 5px;
  border: 1px solid var(--sc-white-dark);
  z-index: 99;
}
.categories h3 {
  cursor: pointer;
  gap: 10px;
  font-size: 15px;
}
span {
  transition: all 0.2s ease-in-out;
}
h3.active span {
  transition: all 0.2s ease-in-out;
  transform: rotate(180deg);
}

ul {
  position: absolute;
  top: 28px;
  background: var(--pm-blue-black);
  width: 100%;
  gap: 10px;
  padding: 10px 0px;
  list-style: none;
  margin-top: 5px;
  animation: dropdown 0.5s forwards;
  overflow: hidden;
}
li {
  cursor: pointer;
  width: 80%;
  text-align: center;
  transition: all 0.2s ease-in-out;
}
li:hover {
  color: var(--pm-blue-black);
  background: var(--pm-white);
}
.search-bar {
  height: 100%;
  flex: 1;
}
.search-bar span {
  background: var(--pm-red);
  cursor: pointer;
  height: 100%;
  width: 40px;
  border-top-right-radius: 5px;
  border-bottom-right-radius: 5px;
}
input {
  background: transparent;
  border: none;
  padding: 0px 20px;
  outline: none;
  height: 100%;
  flex: 1;
  color: var(--pm-white);
  border-top: 1px solid var(--sc-white-dark);
  border-bottom: 1px solid var(--sc-white-dark);
}
@keyframes dropdown {
  0% {
    height: 0;
  }
  /* 50%{height: 100px;} */
  100% {
    height: 283px;
  }
}

@media screen and (max-width: 812px) {
  .search-container {
    width: 300px;
  }
  .categories h3 {
    font-size: 10px;
  }
  input {
    padding: 0 10px;
    width: 60%;
  }
  .categories {
    width: 40%;
  }
  .desktop-nav {
    display: none;
  }
  .mini-nav {
    display: flex;
  }
}
</style>
