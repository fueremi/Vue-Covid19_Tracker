<template>
  <div class="home">
    <Header />
    <main v-if="!loading">
      <b-container>
        <CountrySelect @get-country="getCountryData" :countries="countries" /> 

        <DataTitle :title="location" :time="time" />

        <DataBoxes :stats="stats" />
      </b-container>
    </main>

    <main v-else class="d-flex text-center">
      <p class="text-center">Fetching Data</p>
      <img :src="require('../assets/hourglass.gif')" class="w-24 m-auto" />
    </main>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header";
import DataTitle from "@/components/DataTitle";
import CountrySelect from "@/components/CountrySelect"

export default {
  name: "Home",
  components: {
    Header,
    DataTitle,
    CountrySelect,
    DataBoxes: () => import("@/components/DataBoxes"),
  },
  data() {
    return {
      location: "Global",
      time: "",
      stats: [],
      countries: [],
      loading: true,
    };
  },
  methods: {
    getCountryData(country) {
      this.stats = country;
      this.location = country.Country;
    },
    async clearCountryData() {
      this.location = "Global";
      this.stats = this.$store.state.data.data.Global;
    },
  },
  created() {
    fetch("https://api.covid19api.com/summary")
      .then((res) => res.json())
      .then((res) => {
        this.time = res.Date;
        this.stats = res.Global;
        this.countries = res.Countries;
        this.loading = false;
      });
  },
};
</script>
