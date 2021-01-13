<template>
  <div>
    <h1 class="display-1 text-xs-center">Weather App</h1>

    <v-flex>
      <v-card color="blue-grey darken-2" dark>
        <v-card-text>
          <v-layout justify-center>
            <v-flex xs4 class="text-xs-center">
              <h4>Temperature</h4>
              <h1 class="display-1">{{ weather.name }}</h1>
              <img :src="icon" alt="weather icon" />
              <p>
                <span class="cption mt-4">{{
                  weather.weather[0].description
                }}</span>
              </p>
              <v-flex>
                <v-flex xs8 class="text-xs-center">
                  <h4>Wind And Pressure:</h4>
                  <h3 class="headline">
                    Wind: {{ weather.wind.speed }} m/s({{
                      weather.wind.deg
                    }}&deg;)
                  </h3>
                  <h3 class="headline mt-4">
                    Humidity: {{ weather.main.humidity }} %
                  </h3>
                  <h3 class="headline mt-4">
                    Pressure: {{ weather.main.pressure }} hPa
                  </h3>
                </v-flex>

                <v-flex xs8 class="text-xs-center">
                  <h4>other:</h4>
                  <h3 class="headline mt-4">
                    Max Temperature:{{
                      Math.round(weather.main.temp_max - 273)
                    }}
                    &deg;c
                  </h3>

                  <h3 class="headline mt-4">
                    Min Temperature:{{
                      Math.round(weather.main.temp_min - 273)
                    }}
                    &deg;c
                  </h3>
                </v-flex>
              </v-flex>
            </v-flex>
          </v-layout>
        </v-card-text>
      </v-card>
    </v-flex>

    <v-flex xs12 class="mt-4">
      <v-form @submit.prevent="getWeatherInfo">
        <v-text-field
          v-model="City"
          label="Enter City Name"
          solo
        ></v-text-field>
      </v-form>
    </v-flex>
  </div>
</template>

<script>
export default {
  data() {
    return {
      City: "London",
      weather: {}
    };
  },
  computed: {
    icon() {
      return this.weather.weather
        ? `https://openweathermap.org/img/w/${this.weather.weather[0].icon}.png`
        : "";
    }
  },

  asyncData({ params, $axios }) {
    return $axios
      .$get(
        `https://api.openweathermap.org/data/2.5/weather?q=London&appid=${process.env.weatherAppId}`
      )
      .then(res => {
        return {
          weather: res
        };
      });
  },
  methods: {
    getWeatherInfo() {
      this.$axios
        .$get(
          `https://api.openweathermap.org/data/2.5/weather?q=${this.City}&appid=${process.env.weatherAppId}`
        )
        .then(res => (this.weather = res));
    }
  }
};
</script>
<style lang="scss" scoped></style>
