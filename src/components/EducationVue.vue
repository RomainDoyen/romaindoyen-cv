<template>
  <div class="articles">
    <h2 id="formation">{{ msg }}</h2>
    <div v-for="(educ, i) in educs" :key="i">
      <div class="sous-articles">
        <div class="box-article">
          <h3 class="ghj">{{ educ.ecole }}</h3>
          <h4 class="ghj">{{ educ.diplome }}</h4>
          <p class="gh">{{ educ.date }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EducationVue",
  props: {
    msg: String
  },
  data: () => ({
    educs: [
      {
        ecole: 'Université De La Réunion - Sainte-Clotilde',
        diplome: 'Licence : Informatique',
        date: '2016-08 - 2021-07'
      },
      {
        ecole: 'Lycée Marie Curie - Saint-Anne',
        diplome: 'Baccalauréat Technologique : Science Et Technologie Sante Sociale',
        date: '2014-09 - 2016-07'
      },
      {
        ecole: 'Collège Thérésien Cadet - Sainte-Rose',
        diplome: 'Diplôme Du Brevet',
        date: '2008-09 - 2012-06'
      },
    ]
  })
};
</script>

<style>
.box-article {
  padding: 3em 4em;
  margin: 15px;
  border-radius: 10px;
  display: grid;
}

.ghj {
  margin-top: 12px;
}

h3.ghj {
  color: #273f5b;
  text-decoration: dotted;
}
</style>