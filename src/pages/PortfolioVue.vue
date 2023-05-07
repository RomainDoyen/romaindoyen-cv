<template>
  <div class="articles">
    <h2 id="portfolio"> 📸 {{ msg }}</h2>
        <div class="cot">
          <div class="box-article art" v-for="projet in projets" :key="projet.id">
            <h3>{{ projet.title }}</h3>
            <h4>{{ projet.description }}</h4>
            <p>Technologie utilisé : <span class="techno">{{ projet.techno }}</span></p>
            <img :src="require(`../assets/${projet.img}`)" alt="projet">
            <div v-if="projet?.link" class="link">
              <a class="link-projet" target="_blank" :href="projet.link">Voir le projet</a>
            </div>
          </div>
        </div>
      <div class="sous-articles">
        <a href="https://github.com/RomainDoyen" target="_blank"><i class="fa fa-github" aria-hidden="true"></i>&nbsp; Mon Github</a>
      </div>
  </div>
</template>

<script>
export default {
    name: "PortfolioVue",
    props: {
        msg: String
    },
    data: () => ({
      projets: [
        {
          id: '0',
          title: '🎨 Design And Creation',
          description: 'Portfolio de dessins et logo',
          techno: 'React JS, Firebase',
          img: 'dac.webp',
          link: 'https://designandcreation.netlify.app/'
        },
        {   
          id: '1',
          title: '🍔 Dodo Cuisto (Application mobile)',
          description: 'Application de recette créole',
          techno: 'Java, XML, SQLite',
          img: 'dc.webp',
        },
        {
          id: '2',
          title: '☀️ Weather App (version Web)',
          description: 'Obtenir la météo par le biais d\'une API',
          techno: 'Vue JS, OpenWeatherMap',
          img: 'weather-app.png',
          link: 'https://times-app.netlify.app/'
        },
        {
          id: '3',
          title: '☀️ Weather App (version Mobile)',
          description: 'Obtenir la météo par le biais d\'une API',
          techno: 'React Native, OpenWeatherMap',
          img: 'weather-app-phone.png',
        },
        {
          id: '4',
          title: '💫 Astrologie 23',
          description: 'Projet réaliser dans le cadre scolaire',
          techno: 'HTML, CSS, JS, JQUERY',
          img: 'astrologie23.png',
          link: 'https://vingt-trois.netlify.app/'
        },
      ],
  }),
};
</script>

<style>
.box-article {
  background-color: #d1d1d1;
  padding: 3em 4em;
  margin: 15px;
  border-radius: 10px;
  display: grid;
}

.cot {
  display: inline-flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: 50px;
}

div.art img {
  width: 300px;
  font-size: 20px;
  margin-bottom: 25px;
  background-size: cover;
  border-radius: 5px;
}

.art h3 {
  font-weight: bold;
  text-decoration: underline;
  margin-bottom: 10px;
}

.art h4, p {
  font-style: italic;
  margin-bottom: 15px;
}

.link-projet {
    text-decoration: none;
    color: #3a77c7;
    padding: 17px;
    border-radius: 10px;
    background-color: #b5b5b5;
    font-size: 1vw;
    transition: 0.35s ease-out;
}

.link-projet:hover {
  color: #b5b5b5;
  background-color: #3a77c7;
}

.techno {
  font-weight: bold;
  text-transform: uppercase;
  color: blueviolet;
}

@media only screen and (max-width: 1110px) {
  div.cot, div.art img {
    flex-wrap: wrap;
  }
  .link-projet {
    font-size: 2vw;
  }
}

@media only screen and (max-width: 420px) {
  .link-projet {
    font-size: 3vw;
  }
}
</style>
