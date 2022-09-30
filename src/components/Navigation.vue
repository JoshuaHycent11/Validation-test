<template>
  <header class="bg-light shadow " :class="{ '': scrollNav }">
    <nav class="d-flex align-items-center">
      <div class="branding">
       <h3 class="fw-7">Validation</h3>
      </div>
      <ul v-show="!mobile" class="navigation">
         <li>
          <router-link to="/kodehauz">KodeHauz</router-link>
        </li>
         <li>
          <router-link to="/homeview">Country</router-link>
        </li>
        <div class="d-flex justify-content-center align-items-center">
            <i class=' bx bx-moon mr-2'></i>
            <h6 class="fw-bold">Dark Mode</h6>
        </div>
       
      </ul>
      <div class="icon">
        <i
          @click="toggleMobileNave"
          v-show="mobile"
          class="bx bx-menu"
          :class="{ 'icon-active': mobileNav }"
        ></i>
      </div>
      <transition name="moblie-nav">
        <ul class="dropdown-nav" v-show="mobileNav">
          <li>
            <router-link class="your" to="/">Home</router-link>
          </li>
          <li>
            <router-link class="your" to="/">About</router-link>
          </li>
          <li>
            <router-link class="your" to="/">Portfolio</router-link>
          </li>
          <li>
            <router-link class="your" to="/">Contact</router-link>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<script>
export default {
  name: "navigation",
  data() {
    return {
      scrollNav: null,
      mobile: null,
      mobileNav: null,
      windowWidth: null,
    };
  },
  created() {
    window.addEventListener("resize", this.chechScreen);
    this.chechScreen();
  },

  mounted() {
    window.addEventListener("scroll", this.chechScreen);
  },
  methods: {
    toggleMobileNave() {
      this.mobileNav = !this.mobileNav;
    },
    updateScroll() {
      const scrollPosition = window.scrollY;
      if (scrollPosition > 50) {
        this.scrollNav = true;
        return;
      }
      this.scrollNav = false;
    },

    chechScreen() {
      this.windowWidth = window.innerWidth;
      if (this.windowWidth <= 750) {
        this.mobile = true;
        return;
      }
      this.mobile = false;
      this.mobileNav = false;
      return;
    },

  
  },
};
</script>

<style scoped>

header {
 
  z-index: 99;
  width: 100%;
  position: fixed;
  transition: 0.5s ease all;
  color: #000;
}
ul,
.link {
  font-weight: 500;
  color: #000;
  list-style: none;
  text-decoration: none;
}

ul,
.your {
  list-style: none;
  text-decoration: none;
  color: #000;
}
nav {
  position: relative;
  display: flex;
  flex-direction: row;
  padding: 8px 0;
  transition: 0.5s ease all;
  width: 90%;
  margin: 0 auto;
  @media (min-width: 148px) {
    max-width: 1140px;
  }
}
li {
  text-transform: uppercase;
  padding: 16px;
  margin-left: 16px;
}
.branding {
  display: flex;
  align-items: center;
}

.navigation {
  display: flex;
  align-items: center;
  flex: 1;
  justify-content: flex-end;
}

img {
  width: 50px;
  transition: 0.5s ease all;
}
.link {
  font-size: 14px;
  transition: 0.5s ease all;
  padding-bottom: 4px;
  border-bottom: 1px solid transparent;
  
}

.your {
  font-size: 14px;
  font-weight: 590;
  transition: 0.5s ease all;
  padding-bottom: 4px;
  border-bottom: 2px solid transparent;
}

.your:hover {
  color: #000;
  border-color: #000;
}

.link:hover {
  color: #08afea;
  
}

.icon {
  display: flex;
  align-items: center;
  position: absolute;
  top: 0;
  right: 24px;
  height: 100%;
}

i {
  font-size: 24px;
  cursor: pointer;
  transition: 0.8s ease all;
}

.icon-active {
  transform: rotate(180deg);
}

.dropdown-nav {
  display: flex;
  flex-direction: column;
  position: fixed;
  width: 100%;
  max-width: 180px;
  height: 100%;
  background-color: #fff;
  top: 0;
  left: 0;
}

li {
  margin-left: 0;
}
.orange{
  background: black;
  color: white;
}
</style>