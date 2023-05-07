<template>
  <div class="articles">
    <h2> 👨🏽‍🎓 {{ msg }}</h2>
    <div v-for="(post, i) in posts" :key="i">
      <div class="sous-articles">
        <div class="box-article">
          <p class="gh">{{ post.articles }}</p>
        </div>
      </div>
      <div class="sous-articles">
        <a href="/files/romain-doyen-cv.pdf" download="romain-doyen-cv.pdf"><i class="fa fa-file-pdf-o" aria-hidden="true"></i>&nbsp;{{ post.cv }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "IntroVue",
  props: {
    msg: String
  },
  data: () => ({
    posts: [
      {
        articles: "Étudiant en Informatique et passionné par les domaines du développements (web front-end, design UI / UX, mobile) et de la maintenance informatique.",
        cv: "Télécharger mon CV",
      },
    ],
  }),
};
</script>

<style>
div.articles {
  margin: auto;
  width: 80%;
  margin-bottom: 30px;
  border-radius: 5px;
}

@media only screen and (max-width: 1170px) {
  div.articles {
    width: 100%;
  }
}
</style>