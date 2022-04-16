<template>
  <div class="articles">
    <h2 id="competence">{{ msg }}</h2>
    <div class="skills-bar">
      <div class="bar" v-for="(skill, i) in skills" :key="i">
        <div class="info">
          <span><img v-bind:src="require(`@/images/${skill.icon}`)" /></span>
        </div>
        <div class="title"><span>{{ skill.title }}</span></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SkillsVue",
  props: {
    msg: String
  },
  data : () => ({
    skills: [
      {
        title: 'HTML',
        icon : 'html-5.webp',
      },
      {
        title: 'CSS',
        icon : 'css3.webp',
      },
      {
        title: 'JavaScript',
        icon : 'javascript.webp',
      },
      {
        title: 'PHP',
        icon: 'php.webp',
      },
      {
        title: 'Photoshop',
        icon: 'photoshop.webp',
      },
      {
        title: 'Illustrator',
        icon: 'illustrator.webp',
      },
      {
        title: 'Figma',
        icon: 'figma.webp',
      },
      {
        title: 'MySQL',
        icon: 'mysql.webp',
      },
      {
        title: 'Github',
        icon: 'github.webp',
      },
      {
        title: 'Wordpress',
        icon: 'wordpress.webp',
      },
      {
        title: 'Android',
        icon: 'android-studio.webp',
      },
    ]
  })
};
</script>

<style>
h2 {
  text-align: center;
  text-transform: uppercase;
  padding: 0.6em 1em;
  border-radius: 50px;
}
.skills-bar {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  margin-bottom: 50px;
}
.bar {
  padding: 40px;
}
.bar img {
  width: 110px;
}
.title {
  text-align: center;
  font-weight: 550;
  font-size: 20px;
}
</style>