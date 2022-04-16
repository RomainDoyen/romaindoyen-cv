<template>
  <div class="articles">
    <h2 id="portfolio">{{ msg }}</h2>
    <div v-for="(port, i) in ports" :key="i">
      <div class="sous-articles">
        <div class="cot">
          <div class="box-article art">
            <img v-bind:src="require(`@/images/${port.img_1}`)">
          </div>
          <div class="box-article art">
            <img v-bind:src="require(`@/images/${port.img_2}`)">
          </div>
        </div>
      </div>

      <div class="sous-articles">
        <a href="https://github.com/RomainDoyen" target="_blank"><i class="fa fa-github" aria-hidden="true"></i>&nbsp;{{ port.git }}</a>
      </div>
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
    ports: [
      {
        img_1: 'dac.webp',
        img_2: 'dc.webp',
        git: 'Mon Github' 
      }
    ]
  })
};
</script>

<style>
div.cot, div.art img {
  width: 100%;
  display: inline;
  justify-content: center;
  align-items: center;
  height: auto;
  border-radius: 5px;
  position: relative;
  overflow: hidden;
  text-decoration: none;
}

div.art img {
  background-size: cover;
}
</style>