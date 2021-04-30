<template>
  <div>
    <b-row>
      <b-col md>
        <b-jumbotron bg-variant="warning" header="Cases">
          <div class="mb-1">
            <span>New:</span>
            {{ numberWithCommas(stats.NewConfirmed) }}
          </div>
          <div>
            <span>Total:</span>
            {{ numberWithCommas(stats.TotalConfirmed) }}
          </div>
        </b-jumbotron>
      </b-col>
      <b-col md>
        <b-jumbotron bg-variant="danger" header="Deaths">
          <div class="mb-1">
            <span>New:</span>
            {{ numberWithCommas(stats.NewDeaths) }}
          </div>
          <div>
            <span>Total:</span>
            {{ numberWithCommas(stats.TotalDeaths) }}
          </div>
        </b-jumbotron>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  name: 'DataBoxes',
  props: ['stats'],
  methods: {
    numberWithCommas(x) {
      let data = x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')
      return data
    },
  },
  mounted(){
    console.log('Databoxes - Mounted')
  }
};
</script>

<style scoped>
.display-3 {
  font-weight: bolder;
  font-size: 2rem;
  text-align: center !important;
}

.jumbotron {
  text-align: center;
}

.jumbotron span {
  font-weight: bold;
}
</style>