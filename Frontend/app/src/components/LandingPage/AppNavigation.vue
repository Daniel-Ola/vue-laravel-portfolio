<template>
  <nav class="container mx-auto">
    <!--  Desktop Menu  -->
    <div class="flex items-center">
      <div class="app-logo w-32">
        <router-link :to="{ name: 'home' }">
          <img :src="$store.state.appLogo" alt="App Logo" />
        </router-link>
      </div>
      <div
        class="container sm:flex hidden items-center justify-end mx-auto gap-10"
      >
        <app-nav-menu-list
          v-for="(nav, index) in linkList"
          :class="checkActiveRoute(nav.url)"
          :key="index"
          :nav="nav"
        />
      </div>
      <div class="flex md:hidden justify-end items-center container">
        <button @click="showMobileMenu = !showMobileMenu">
          <i class="fa fa-bars text-3xl"></i>
        </button>
      </div>
    </div>
    <!--  Mobile Menu -->
    <XyzTransition appear xyz="fade in-left-100% out-right-100%" mode="out-in">
      <div
        class="absolute right-0 w-1/2 bg-app-blue z-10 flex flex-col md:hidden"
        v-show="showMobileMenu"
      >
        <app-nav-menu-list
          v-for="(nav, index) in linkList"
          :class="checkActiveRoute(nav.url)"
          :key="index"
          :nav="nav"
        />
      </div>
    </XyzTransition>
  </nav>
</template>

<script>
import AppNavMenuList from "@/components/LandingPage/AppNavMenuList";

// import { ref } from "vue";

// const showMobileMenu = ref(false);

export default {
  name: "AppNavigation",
  components: {
    AppNavMenuList,
  },
  data() {
    return {
      showMobileMenu: false,
      linkList: [
        {
          title: "About Me",
          url: "about",
        },
        {
          title: "Resume",
          url: "about",
        },
        {
          title: "Study Case",
          url: "personal.info",
        },
        {
          title: "Portfolio",
          url: "resume",
        },
        {
          title: "Portfolio 2",
          url: "resume.info",
        },
      ],
    };
  },
  methods: {
    checkActiveRoute(routeName) {
      return this.$route.name === routeName
        ? "btn-primary text-white"
        : "text-[#42B983]";
    },
  },
  computed: {
    appLogo() {
      return this.$store.state.appLogo;
    },
  },
};
</script>
