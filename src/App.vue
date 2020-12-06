<template>
  <div id="main" :class="isNight ? 'night' : 'day'">
    <div id="container">
      <h1 id="weather-text">Météo</h1>
      <form class="search-location" v-on:submit.prevent="getWeather">
        <input
          type="text"
          class="citySerach"
          placeholder="Choisissez votre ville"
          v-model="inputSearch"
          autocomplete="off"
        />
      </form>
      <div class="carte-weather">
        <div id="firstCard" :class="isClear1 ? 'clear' : 'weather-infos'">
          <div id="city">
            <span>{{ weather.cityName }}</span>
            <img
              :src="
                isClear1
                  ? 'https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png'
                  : 'https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png'
              "
            />
          </div>
          <div>
            <span id="date">{{ weather.date }}</span>
          </div>
          <span id="description">{{ weather.description }}</span
          ><br />
          <div id="temperature">
            <p>{{ weather.temperature }} °C</p>
          </div>
          <span id="temp_min">Min : {{ weather.min }}</span> °C
          <span id="temp_max">Max : {{ weather.max }}</span> °C<br />
          <span id="pressure">Pression : {{ weather.pressure }}</span>
          <div id="humidity-wind">
            <span>Humidité : {{ weather.humidity }} %</span>
            <span>Vent : {{ weather.wind }} KM/H</span>
          </div>
        </div>

        <div :class="isClear2 ? 'clear' : 'weather-infos'">
          <div id="city">
            <span>{{ weather2.cityName }}</span>
            <img
              :src="
                isClear2
                  ? 'https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png'
                  : 'https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png'
              "
            />
          </div>
          <div>
            <span id="date">{{ weather.dateNext(1) }}</span>
          </div>
          <span id="description">{{ weather2.description }}</span
          ><br />
          <div id="temperature">
            <p>{{ weather2.temperature }} °C</p>
          </div>
          <span id="temp_min">Min : {{ weather2.min }}</span> °C
          <span id="temp_max">Max : {{ weather2.max }}</span> °C<br />
          <span id="pressure">Pression : {{ weather2.pressure }}</span>
          <div id="humidity-wind">
            <span>Humidité : {{ weather2.humidity }} %</span>
            <span>Vent : {{ weather2.wind }} KM/H</span>
          </div>
        </div>

        <div :class="isClear3 ? 'clear' : 'weather-infos'">
          <div id="city">
            <span>{{ weather3.cityName }}</span>
            <img
              :src="
                isClear3
                  ? 'https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png'
                  : 'https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png'
              "
            />
          </div>
          <div>
            <span id="date">{{ weather.dateNext(2) }}</span>
          </div>
          <span id="description">{{ weather3.description }}</span
          ><br />
          <div id="temperature">
            <p>{{ weather3.temperature }} °C</p>
          </div>
          <span id="temp_min">Min : {{ weather3.min }}</span> °C
          <span id="temp_max">Max : {{ weather3.max }}</span> °C<br />
          <span id="pressure">Pression : {{ weather3.pressure }}</span>
          <div id="humidity-wind">
            <span>Humidité : {{ weather3.humidity }} %</span>
            <span>Vent : {{ weather3.wind }} KM/H</span>
          </div>
        </div>

        <div :class="isClear4 ? 'clear' : 'weather-infos'">
          <div id="city">
            <span>{{ weather4.cityName }}</span>
            <img
              :src="
                isClear4
                  ? 'https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png'
                  : 'https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png'
              "
            />
          </div>
          <div>
            <span id="date">{{ weather.dateNext(3) }}</span>
          </div>
          <span id="description">{{ weather4.description }}</span
          ><br />
          <div id="temperature">
            <p>{{ weather4.temperature }} °C</p>
          </div>
          <span id="temp_min">Min : {{ weather4.min }}</span> °C
          <span id="temp_max">Max : {{ weather4.max }}</span> °C<br />
          <span id="pressure">Pression : {{ weather4.pressure }}</span>
          <div id="humidity-wind">
            <span>Humidité : {{ weather4.humidity }} %</span>
            <span>Vent : {{ weather4.wind }} KM/H</span>
          </div>
        </div>

        <div :class="isClear5 ? 'clear' : 'weather-infos'">
          <div id="city">
            <span>{{ weather5.cityName }}</span>
            <img
              :src="
                isClear5
                  ? 'https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png'
                  : 'https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png'
              "
            />
          </div>
          <div>
            <span id="date">{{ weather.dateNext(4) }}</span>
          </div>
          <span id="description">{{ weather5.description }}</span
          ><br />
          <div id="temperature">
            <p>{{ weather5.temperature }} °C</p>
          </div>
          <span id="temp_min">Min : {{ weather5.min }}</span> °C
          <span id="temp_max">Max : {{ weather5.max }}</span> °C<br />
          <span id="pressure">Pression : {{ weather5.pressure }}</span>
          <div id="humidity-wind">
            <span>Humidité : {{ weather5.humidity }} %</span>
            <span>Vent : {{ weather5.wind }} KM/H</span>
          </div>
        </div>

        <div :class="isClear6 ? 'clear' : 'weather-infos'">
          <div id="city">
            <span>{{ weather6.cityName }}</span>
            <img
              :src="
                isClear6
                  ? 'https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png'
                  : 'https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png'
              "
            />
          </div>
          <div>
            <span id="date">{{ weather.dateNext(5) }}</span>
          </div>
          <span id="description">{{ weather6.description }}</span
          ><br />
          <div id="temperature">
            <p>{{ weather6.temperature }} °C</p>
          </div>
          <span id="temp_min">Min : {{ weather6.min }}</span> °C
          <span id="temp_max">Max : {{ weather6.max }}</span> °C<br />
          <span id="pressure">Pression : {{ weather6.pressure }}</span>
          <div id="humidity-wind">
            <span>Humidité : {{ weather6.humidity }} %</span>
            <span>Vent : {{ weather6.wind }} KM/H</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
 
  data() {
    return {
      inputSearch: "",
      isClear1: false,
      isClear2: false,
      isClear3: false,
      isClear4: false,
      isClear5: false,
      isClear6: false,
      isNight: false,
      imageSun:
        "https://cdn.pixabay.com/photo/2017/02/19/22/16/sun-2081066_960_720.png",
      imageCloud:
        "https://cdn.pixabay.com/photo/2013/04/01/09/22/clouds-98536_960_720.png",
      weather: {
        cityName: "-------",
        date: new Date().toLocaleDateString("fr-FR"),
        dateNext: function getDate(n) {
          const date = new Date();
          date.setDate(date.getDate() + n);
          const next = date.toLocaleDateString("fr-FR");
          return next;
        },
        country: "--",
        temperature: "00",
        description: "--------",
        min: "00",
        max: "00",
        humidity: "00",
        pressure: "000",
        wind: "00",
      },
      //------------------
      weather2: {
        cityName: "-------",
        country: "--",
        temperature: "00",
        description: "--------",
        min: "00",
        max: "00",
        humidity: "00",
        pressure: "000",
        wind: "00",
      },
      //---------------------
      weather3: {
        cityName: "-------",
        country: "--",
        temperature: "00",
        description: "--------",
        min: "00",
        max: "00",
        humidity: "00",
        pressure: "000",
        wind: "00",
      },
      //----------------------
      weather4: {
        cityName: "-------",
        country: "--",
        temperature: "00",
        description: "--------",
        min: "00",
        max: "00",
        humidity: "00",
        pressure: "000",
        wind: "00",
      },
      //-----------------------
      weather5: {
        cityName: "-------",
        country: "--",
        temperature: "00",
        description: "--------",
        min: "00",
        max: "00",
        humidity: "00",
        pressure: "000",
        wind: "00",
      },
      //------------------------
      weather6: {
        cityName: "-------",
        country: "--",
        temperature: "00",
        description: "--------",
        min: "00",
        max: "00",
        humidity: "00",
        pressure: "000",
        wind: "00",
      },
    };
  },
  methods: {
    getWeather: async function () {
      console.log(this.inputSearch);
      const API_KEY = "3e0c41b12cfc912784962605e33a6b44";
      const baseUrl = `https://api.openweathermap.org/data/2.5/find?q=${this.inputSearch}&lang=fr&cnt=7&appid=${API_KEY}&units=metric`;
      const response = await fetch(baseUrl);
      const data = await response.json();
      const listData = await data.list;
      console.log(listData);
      this.inputSearch = "";
      //Day 1:
      this.weather.cityName = listData[0].name;
      this.weather.temperature = Math.round(listData[0].main.temp);
      this.weather.description = listData[0].weather[0].description;
      this.weather.min = Math.round(listData[0].main.temp_min);
      this.weather.max = Math.round(listData[0].main.temp_max);
      this.weather.humidity = listData[0].main.humidity;
      this.weather.pressure = listData[0].main.pressure;
      this.weather.wind = Math.round(listData[0].wind.speed);

      //Day 2 :
      this.weather2.cityName = listData[1].name;
      this.weather2.temperature = Math.round(listData[1].main.temp);
      this.weather2.description = listData[1].weather[0].description;
      this.weather2.min = Math.round(listData[1].main.temp_min);
      this.weather2.max = Math.round(listData[1].main.temp_max);
      this.weather2.humidity = listData[1].main.humidity;
      this.weather2.pressure = listData[1].main.pressure;
      this.weather2.wind = Math.round(listData[1].wind.speed);

      //Day 3 :
      this.weather3.cityName = listData[2].name;
      this.weather3.temperature = Math.round(listData[2].main.temp);
      this.weather3.description = listData[2].weather[0].description;
      this.weather3.min = Math.round(listData[2].main.temp_min);
      this.weather3.max = Math.round(listData[2].main.temp_max);
      this.weather3.humidity = listData[2].main.humidity;
      this.weather3.pressure = listData[2].main.pressure;
      this.weather3.wind = Math.round(listData[2].wind.speed);

      // Day 4 :
      this.weather4.cityName = listData[3].name;
      this.weather4.temperature = Math.round(listData[3].main.temp);
      this.weather4.description = listData[3].weather[0].description;
      this.weather4.min = Math.round(listData[3].main.temp_min);
      this.weather4.max = Math.round(listData[3].main.temp_max);
      this.weather4.humidity = listData[3].main.humidity;
      this.weather4.pressure = listData[3].main.pressure;
      this.weather4.wind = Math.round(listData[3].wind.speed);

      // Day 5 :
      this.weather5.cityName = listData[4].name;
      this.weather5.temperature = Math.round(listData[4].main.temp);
      this.weather5.description = listData[4].weather[0].description;
      this.weather5.min = Math.round(listData[4].main.temp_min);
      this.weather5.max = Math.round(listData[4].main.temp_max);
      this.weather5.humidity = listData[4].main.humidity;
      this.weather5.pressure = listData[4].main.pressure;
      this.weather5.wind = Math.round(listData[4].wind.speed);

      // Day 6 :
      this.weather6.cityName = listData[5].name;
      this.weather6.temperature = Math.round(listData[5].main.temp);
      this.weather6.description = listData[5].weather[0].description;
      this.weather6.min = Math.round(listData[5].main.temp_min);
      this.weather6.max = Math.round(listData[5].main.temp_max);
      this.weather6.humidity = listData[5].main.humidity;
      this.weather6.pressure = listData[5].main.pressure;
      this.weather6.wind = Math.round(listData[5].wind.speed);

      //time of day :
      const timeOfDay = listData[0].weather[0].icon;
      if (timeOfDay.includes("d")) {
        this.isNight = false;
      } else {
        this.isNight = true;
      }
      console.log("isDay", timeOfDay);

      //Description day :

      const descriptionDay1 = listData[0].weather[0].main;
      console.log(descriptionDay1);
      if (descriptionDay1.includes("Clear")) {
        this.isClear1 = true;
      } else {
        this.isClear1 = false;
      }
      console.log(descriptionDay1);
      const descriptionDay2 = listData[1].weather[0].main;
      if (descriptionDay2.includes("Clear")) {
        this.isClear2 = true;
      } else {
        this.isClear2 = false;
      }
      console.log(descriptionDay2);
      const descriptionDay3 = listData[2].weather[0].main;
      if (descriptionDay3 === "Clear") {
        this.isClear3 = true;
      } else {
        this.isClear3 = false;
      }
      const descriptionDay4 = listData[3].weather[0].main;
      if (descriptionDay4 === "Clear") {
        this.isClear4 = true;
      } else {
        this.isClear4 = false;
      }
      const descriptionDay5 = listData[4].weather[0].main;
      if (descriptionDay5 === "Clear") {
        this.isClear5 = true;
      } else {
        this.isClear5 = false;
      }
      const descriptionDay6 = listData[5].weather[0].main;
      if (descriptionDay6 === "Clear") {
        this.isClear6 = true;
      } else {
        this.isClear6 = false;
      }
      console.log(descriptionDay1);
    },
  },
};
</script>

<style>
@import "./assets/style.css";
</style>
