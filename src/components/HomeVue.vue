<template>
  <div class="home--vue">
    <header>
      <div class="head-motion">
        <img id="head-ban" src="../images/header.webp" />
      </div>
      <div class="head">
        <img class="logo" src="../images/rd.webp" />
        <h1>{{ msg }}</h1>
        <p>{{ msg_p }}</p>
      </div>
    </header>

    <div class="motion_menu">
        <div class="menu">
            <ul>
                <li><a href="#home"><i class="fa fa-home" aria-hidden="true"></i>&nbsp;Acceuil</a></li>
                <li><a href="#competence"><i class="fa fa-code" aria-hidden="true"></i>&nbsp;Compétences</a></li>
                <li><a href="#portfolio"><i class="fa fa-book" aria-hidden="true"></i>&nbsp;Portfolio</a></li>
                <li><a href="#experience"><i class="fa fa-user-plus" aria-hidden="true"></i>&nbsp;Expériences</a></li>
                <li><a href="#formation"><i class="fa fa-graduation-cap" aria-hidden="true"></i>&nbsp;Formations</a></li>
            </ul>
        </div>
    </div>

    <intro-vue msg="Étudiant en informatique"/>
    <skills-vue msg="Compétences" />
    <portfolio-vue msg="Portfolio"/>
    <experiments-vue msg="Expériences professionelles"/>
    <education-vue msg="Formations"/>
  </div>
</template>

<script>
import IntroVue from './IntroVue.vue';
import SkillsVue from "./SkillsVue.vue";
import ExperimentsVue from "./ExperimentsVue.vue";
import EducationVue from "./EducationVue.vue";
import PortfolioVue from "./PortfolioVue.vue";

export default {
  name: "HomeVue",
  props: {
    msg: String,
    msg_p: String,
  },
  components: {
    IntroVue,
    SkillsVue,
    ExperimentsVue,
    EducationVue,
    PortfolioVue,
  },
};
</script>

<style>
div.motion_menu {
  padding: 50px;
  font-size: 20px;
  list-style: none;
}

div.menu li {
  display: inline;
  margin: 20px;
}

div.menu li a {
  text-decoration: none;
  color: #9A9A9A;
  transition: 0.35s ease-in;
}

div.menu li a:hover { color: #1d1d1d; }

div.head-motion,
div.motion_menu,
div.head, 
div.sous-articles {
  display: flex;
  align-items: center;
  justify-content: center;
}

div.head-motion img#head-ban {
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
}

div.head img.logo,
div.head h1,
div.head p {
  margin: 20px;
}

div.head {
  margin-bottom: 50px;
  margin-top: -150px;
}

img.logo {
  width: 120px;
}

div.head h1 {
  color: #868686;
  text-transform: uppercase;
}

div.head p {
  background-color: #3d545c;
  border-radius: 30px;
  padding: 20px;
  color: #c7a23a;
  font-style: italic;
}

.box-article {
  background-color: #d1d1d1;
  padding: 3em 4em;
  margin: 15px;
  border-radius: 10px;
  display: grid;
}

.gh {
  font-style: oblique;
  margin-top: 12px;
  font-weight: 360;
  line-height: 2em;
  font-size: 20px;
}

div.sous-articles a {
  text-decoration: none;
  color: #C7A23A;
  padding: 17px;
  border-radius: 10px;
  background-color: #d1d1d1;
  font-size: 20px;
  transition: 0.35s ease-out;
  margin-top: 50px;
  margin-bottom: 50px;
}

div.sous-articles a:hover { 
  color: #d1d1d1;
  background-color: #C7A23A; 
}
</style>
