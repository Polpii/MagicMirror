<template>
    <main>
        <Measurements
            :cloudiness="this.forecast.cloudiness"
            :windSpeed="this.forecast.windSpeed"
            :humidity="this.forecast.humidity"
        ></Measurements>

        <Temperature
            :value="this.forecast.temperatureValue"
            :high="this.forecast.temperatureHigh"
            :low="this.forecast.temperatureLow"
        ></Temperature>

        <section class="weather__section">
            <div class="location">{{ forecast.location }}</div>
            <div class="weather__description">{{ forecast.description }}</div>
            <img class="weather__icon" :src="forecast.weatherIcon" alt="Logo de la météo">
        </section>

    </main>
</template>

<script>
import Temperature from './Temperature'
import Measurements from './Measurements'
import WeatherForecast from '../services/WeatherForecast'

export default {
    name: 'WeatherApp',

    components: {
        Temperature,
        Measurements
    },

    data() {
        return {
            forecast: new WeatherForecast
        }
    }
}
</script>

<style scoped>
main {
    width: 100%;
    height: 100%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;

    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;

    box-shadow: 0 19px 38px rgba(0,0,0,0.30), 0 15px 12px rgba(0,0,0,0.22);
}

.app--day {
    background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1)), url('../assets/images/morning.jpg');
}

.app--night {
    background-image: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1)), url('../assets/images/night.jpg');
}

@media screen and (min-width: 450px) {
    main {
        width: 330px;
        height: 600px;

        border-radius: 5px;
    }
}

.weather__section {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.location {
    text-transform: uppercase;
    font-weight: bold;
}

.weather__description {
    text-transform: lowercase;
    margin-left: 10%;
    margin-right: 10%;
    text-align: center;
}

.weather__description:first-letter {
    text-transform: uppercase;
}

.weather__icon {
    width: 12em;
    padding-bottom: 9em;
}
</style>
