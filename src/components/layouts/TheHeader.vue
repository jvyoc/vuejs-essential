<template>
  <div class="navbar navbar-default topnav">
    <div class="container">
      <div class="navbar-header">

          <button type="button" class="navbar-toggle" @click="toggleNav">
          <span class="sr-only">Toggle navigation</span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>

        <a href="/" class="navbar-brand">

            <span class="title" >{{ logo.title }}
            <img :src="logo.src" :alt="logo.title"></span>
        </a>
      </div>


      <div id="top-navbar-collapse" :class="['collapse', 'navbar-collapse', { in: showCollapsedNav }]">
        <ul class="nav navbar-nav">
          <li v-for="(item, index) in navList" :class="{ active: index === activeNavIndex }">
            <a href="#" @click="changeNavIndex(index)">{{ item }}</a>
          </li>
        </ul>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'TheHeader',
  data() {
    return {
      logo: {
        src: `${this.uploadsUrl}csm_teahauslogo_535907d536.png`,
        title: 'VuejsCaff'
      },

      navList: ['社区', '头条', '问答', '教程'],
      activeNavIndex: 0,
       showCollapsedNav: false
    }
  },
  beforeCreate() {
    this.uploadsUrl = 'http://projects-chen.de/fileadmin/_processed_/c/2/'
  },
  methods: {
    changeNavIndex(index) {
      this.activeNavIndex = index
    },
    toggleNav() {
      this.showCollapsedNav = !this.showCollapsedNav
    }
  }
}
</script>

<style scoped>
.title { display:yes; color: blue}
.navbar-default .navbar-nav > .active > a { background: rgba(0,0,0,.03);}
</style>
