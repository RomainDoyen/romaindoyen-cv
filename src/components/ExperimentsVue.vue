<template>
  <div class="articles">
    <h2 id="experience">{{ msg }}</h2>
    <div v-for="(exp,i) in exps" :key="i">
      <section class="timeline">
        <div class="container">
          <div class="timeline-item">
            <div class="timeline-img"></div>
            <div class="timeline-content js--fadeInLeft">
              <h3>{{ exp.subtitle }}</h3>
              <div class="date">{{ exp.date }}</div>
              <h4>{{ exp.lieu }}</h4>
              <p>{{ exp.description.point_1 }}</p>
              <P>{{ exp.description.point_2 }}</P>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "ExperimentsVue",
  props: {
    msg: String
  },
  data: () => ({
    exps: [
      {
        subtitle: 'Réparateur D\'électroménagers',
        date: '2021-01 - 2021-01',
        lieu: 'Electro-Dep, Saint-Anne, Il De La Réunion',
        description: {
          point_1: '• Réparation quotidienne d\'appareil électroménager',
          point_2: '• Localisation précise de la défaillance et identification de ses causes en démontant précautionneusement l\'appareil et en utilisant des outils de mesure et de diagnostic comme le multimètre.'
        }
      },
    ]
  })
};
</script>

<style>
.timeline {
  position: relative;
}
.timeline::before {
  content: "";
  background: #C5CAE9;
  width: 5px;
  height: 95%;
  position: absolute;
  left: 50%;
  border-radius: 10px;
  transform: translateX(-50%);
}
.timeline-item {
  width: 100%;
  margin-bottom: 70px;
}
.timeline-img {
  width: 30px;
  height: 30px;
  background: #3F51B5;
  border-radius: 50%;
  position: absolute;
  left: 50%;
  margin-top: 25px;
  margin-left: -15px;
}
.timeline-content {
  position: relative;
  width: 45%;
  padding: 10px 30px;
  border-radius: 4px;
  background: #f5f5f5;
  box-shadow: 0 20px 25px -15px rgb(0 0 0 / 30%);
}
.timeline-item::after {
  content: "";
  display: block;
  clear: both;
}
.date {
  background: #C7A23A;
  display: inline-block;
  color: #FFFFFF;
  padding: 10px;
  position: absolute;
  top: 0;
  right: 0;
}
.timeline-content::after {
  content: "";
  position: absolute;
  border-style: solid;
  width: 0;
  height: 0;
  top: 30px;
  right: -15px;
  border-width: 10px 0 10px 15px;
  border-color: transparent transparent transparent #f5f5f5;
}
.timeline-item::after {
  content: "";
  display: block;
  clear: both;
}
</style>