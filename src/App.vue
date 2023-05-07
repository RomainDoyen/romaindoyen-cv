<template>
  <div class="container">
    <home-vue msg="Romain Doyen" msgp="CV personnel"/> 
    <footer-vue msg="Réseaux sociaux"/>
    <button @click="scrollToTop" id="myBtn" v-show="scY > 300"><i class="fa fa-chevron-up" aria-hidden="true"></i></button>
  </div>
</template>

<script>
import HomeVue from './components/HomeVue.vue'
import FooterVue from './components/FooterVue.vue'

export default {
  name: 'App',
  components: {
    HomeVue,
    FooterVue
  },
  data() {
    return {
      scTimer: 0,
      scY: 0,
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },
  methods: { 
    handleScroll() {
      if (this.scTimer) return;
      this.scTimer = setTimeout(() => {
        this.scY = window.scrollY;
        clearTimeout(this.scTimer);
        this.scTimer = 0;
      }, 100);
    },
    scrollToTop() {
      window.scrollTo(0,0);
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@200&display=swap');
@import url('https://fonts.googleapis.com/css?family=Quicksand:300,500');
@import url('https://cdn.jsdelivr.net/npm/fork-awesome@1.2.0/css/fork-awesome.min.css');

*, ::before, ::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  position: relative;
}

body, html { 
  font-family: 'Quicksand', sans-serif;
  height: 100%;
  background-color: #dddcdc;
  scroll-behavior: smooth;
}

h1, h2, h3 {
  font-family: 'Montserrat', sans-serif;
}

#myBtn {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 99;
  width: 50px;
  height: 50px;
  font-size: 30px;
  border: none;
  outline: none;
  background: #CAA13D;
  border-radius: 50%;
  color: #283F5C;
  cursor: pointer;
} 
 
#myBtn:hover {
  transition: 0.3s;
  opacity: 0.8;
}

/* Responsive */

@media only screen and (max-width: 1210px){
  .main {
    width:320px;
  }

  .footer-wave-box {
    display: none;
  }

  .single-footer:first-child, .single-footer {
    width: 100%;
  }

  .footer-area {
    margin-top: 0;
    text-align: center;
  }
}

@media only screen and (max-width: 916px) {
  body { word-wrap: break-word; }

  pre { white-space: pre-wrap; }
}

@media only screen and (max-width: 930px) {
  .articles {
    width: auto;
    padding: 0;
  }
}

@media only screen and (max-width: 920px) {
  div.head, 
  div.menu ul, 
  div.pre-footer, 
  div.sous-articles {
    display: flex;
    flex-direction: column;
  }

  div.head {
    margin-top: initial;
    margin-bottom: initial;
  }

  div.motion_menu {
    background-color: #3d545c;
    width: 100%;
    margin-bottom: 25px;
  }
}

@media only screen and (max-width: 600px) {
  .timeline-content {
    width: auto;
  }
  div.art img {
    width: 100%;
    height: auto;
  }
}
</style>
