<template>
  <div id="navbar">
    <div class="nav-brand">
      <h2>Cytonn</h2>
      <i class="fa fa-navicon" v-on:click="display"
        ><img src="../assets/more.png" alt=""
      /></i>
    </div>

    <div class="bar-items" :class="{ hide: !show }">
      <div id="menu">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/login">Login</router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "NavbarComp",
};
</script>

<style>
h1 {
  text-align: center;
  font-size: 36px;
  text-transform: capitalize;
}
h2 {
  padding-left: 15px;
  color: #fff;
  margin: 0;
}

#navbar {
  display: flex;
  align-items: center;
  background-color: #115dd8;
  width: 100%;
}

#menu {
  list-style-type: none;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  width: 100%;
  margin: 0;
  padding: 0;
}

.bar-items {
  width: 100%;
}

a {
  padding: 20px;
}

li:hover {
  background-color: #115dd8;
}

a {
  text-decoration: none;
  font-size: 18px;
  color: #fff;
}

.fa {
  display: none;
}

@media (max-width: 675px) {
  #navbar {
    flex-direction: column;
  }

  .fa {
    display: block;
    padding: 0 25px;
    position: absolute;
    right: 0;
    color: #fff;
    font-size: 30px;
    cursor: pointer;
  }

  #menu {
    flex-direction: column;
    padding: 5px 0;
  }

  a {
    text-align: center;
    width: 100%;
    box-sizing: border-box;
    padding: 15px;
  }

  .hide {
    display: none;
  }

  .nav-brand {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 15px 0px;
    background-color: #115dd8;
  }
}
</style>
<script>
export default {
  data() {
    return { show: false };
  },
  methods: {
    display() {
      console.log("clicked");
      this.show = !this.show;
    },
  },
};
</script>
