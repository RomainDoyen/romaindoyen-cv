<template>
  <div class="articles">
    <h2 id="experience"> 👨🏽‍💼 {{ msg }}</h2>
    <div class="timeline">
      <div v-for="event in events" :key="event.id" class="timeline-item">
        <div class="timeline-content">
          <h3>{{ event.subtitle }}</h3>
          <div class="date-container">
            <span class="date">{{ event.date }}</span>
          </div>
          <h4>{{ event.lieu }}</h4>
          <p>{{ event.description.point_1 }}</p>
          <p>{{ event.description.point_2 }}</p>
        </div>
      </div>
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
    events: [
      {
        id: 0,
        subtitle: '🔧 Réparateur D\'électroménagers',
        date: '2021-01 - 2021-01',
        lieu: 'Electro-Dep, Saint-Anne, Il De La Réunion',
        description: {
          point_1: '• Réparation quotidienne d\'appareil électroménager',
          point_2: '• Localisation précise de la défaillance et identification de ses causes en démontant précautionneusement l\'appareil et en utilisant des outils de mesure et de diagnostic comme le multimètre.'
        }
      },
      {
        id: 1,
        subtitle: 'Stage de développeur web backend',
        date: '2022-02 - 2022-03',
        lieu: 'Flaxib, Sainte-Clotilde, Il De La Réunion',
        description: {
          point_1: '• Stage développeur backend durant deux mois dans l\'entreprise Flaxib, SainteClotilde',
          point_2: '• Stage de deux mois pour la création d\'une application web qui calcule les itinéraires optimal pour les transports scolaires'
        }
      },
    ]
  })
};
</script>

<style>
.timeline {
  margin-top: 30px;
  position: relative;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}

.timeline::before {
  content: "";
  position: absolute;
  top: 0;
  left: 50%;
  width: 5px;
  height: 100%;
  background-color: #788bf4;
  transform: translateX(-50%);
}

.timeline-item {
  position: relative;
  margin-bottom: 30px;
}

.timeline-content {
  position: relative;
  padding: 10px;
  border-radius: 4px;
  line-height: 2rem;
  background: #f5f5f5;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.timeline-content::before {
  content: "";
  position: absolute;
  top: 50%;
  left: -10px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background-color: #3F51B5;
  transform: translateY(-50%);
}

.date-container {
  position: absolute;
  top: 0;
  right: 0px;
  width: 110px;
  text-align: center;
}

.date {
  display: inline-block;
  padding: 6px;
  border-radius: 4px;
  background-color: #C7A23A;
  color: #fff;
}

@media only screen and (max-width: 630px) {
  .date-container {
    display: none;
  }
}
</style>