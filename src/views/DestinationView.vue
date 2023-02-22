<template>
  <main id="destination">
    <HeaderMenu />
    <div class="destination-wrapper">
      <div class="destination-heading">
        <h5>01</h5>
        <h5>PICK YOUR DESTINATION</h5>
      </div>
      <div class="destination-body">
        <div class="left-side">
          <img
            :src="destinationInfo[currentDestination].image"
            alt="destination"
          />
        </div>
        <div class="right-side">
          <div class="nav-wrapper">
            <nav>
              <div
                class="nav-text"
                v-for="destination in destinationInfo"
                :key="destination.name"
                :class="{
                  selected: currentDestination === destination.name,
                }"
                @click="() => (currentDestination = destination.name)"
              >
                {{ destination.name }}
              </div>
            </nav>
          </div>
          <h2>{{ destinationInfo[currentDestination].name }}</h2>
          <div class="body-text">
            {{ destinationInfo[currentDestination].bodyText }}
          </div>
          <hr />
          <div class="planet-info">
            <div class="distance">
              <div class="sub-heading2">AVG. DISTANCE</div>
              <div class="sub-heading1">
                {{ destinationInfo[currentDestination].distance }}
              </div>
            </div>
            <div class="travel-time">
              <div class="sub-heading2">EST. TRAVEL TIME</div>
              <div class="sub-heading1">
                {{ destinationInfo[currentDestination].travelTime }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import HeaderMenu from "@/components/HeaderMenu.vue";
import { ref } from "vue";

interface Destination {
  [name: string]: {
    name: "moon" | "mars" | "europa" | "titan";
    image: string;
    bodyText: string;
    distance: string;
    travelTime: string;
  };
}

const destinationInfo: Destination = {
  moon: {
    name: "moon",
    image: "src/assets/destination/image-moon.png",
    bodyText:
      "See our planet as you’ve never seen it before. A perfect relaxing trip away to help regain perspective and come back refreshed. While you’re there, take in some history by visiting the Luna 2 and Apollo 11 landing sites.",
    distance: "384,400 KM",
    travelTime: "3 DAYS",
  },
  mars: {
    name: "mars",
    image: "src/assets/destination/image-mars.png",
    bodyText:
      "Don’t forget to pack your hiking boots. You’ll need them to tackle Olympus Mons, the tallest planetary mountain in our solar system. It’s two and a half times the size of Everest!",
    distance: "225 MIL. KM",
    travelTime: "9 MONTHS",
  },
  europa: {
    name: "europa",
    image: "src/assets/destination/image-europa.png",
    bodyText:
      "The smallest of the four Galilean moons orbiting Jupiter, Europa is a winter lover’s dream. With an icy surface, it’s perfect for a bit of ice skating, curling, hockey, or simple relaxation in your snug wintery cabin.",
    distance: "628 MIL. KM",
    travelTime: "3 YEARS",
  },
  titan: {
    name: "titan",
    image: "src/assets/destination/image-titan.png",
    bodyText:
      "The only moon known to have a dense atmosphere other than Earth, Titan is a home away from home (just a few hundred degrees colder!). As a bonus, you get striking views of the Rings of Saturn.",
    distance: "1.6 BILL. KM",
    travelTime: "7 YEARS",
  },
};

const currentDestination = ref<"moon" | "mars" | "europa" | "titan">("moon");
</script>

<style scoped lang="scss">
#destination {
  background: url("../assets/destination/background-destination-desktop.jpg")
    no-repeat center center fixed;
  background-size: cover;
  height: 100vh;
  overflow: hidden;
  .destination-wrapper {
    .destination-heading {
      display: flex;
      flex-direction: row;
      gap: 1rem;
      & > h5:nth-child(1) {
        color: white;
        opacity: 0.2;
        font-weight: bold;
      }
      & > h5:nth-child(2) {
        color: white;
      }
    }
    .destination-body {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: 1fr;
      grid-column-gap: 0px;
      grid-row-gap: 0px;
      .left-side {
        grid-area: 1 / 1 / 2 / 2;
        display: grid;
        place-items: center;
        img {
          width: 445px;
          height: 445px;
        }
      }
      .right-side {
        grid-area: 1 / 2 / 2 / 3;
        max-width: 40rem;
        h2 {
          margin: 4rem 0rem 0rem 0rem;
          text-transform: uppercase;
        }

        .planet-info {
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          margin: 2rem 0rem 0rem 0rem;
          max-width: 30rem;
          .distance > div:nth-child(1),
          .travel-time > div:nth-child(1) {
            color: #d0d6f9;
          }
        }
      }
      nav {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        & > div {
          color: #d0d6f9;
          text-transform: uppercase;
          cursor: pointer;
        }
      }
      .nav-text.selected::after,
      .nav-text:not(.selected):hover::after {
        content: "";
        display: block;
        position: relative;
        background-color: white;
        height: 4px;
        width: 100%;
        top: 50%;
        margin: 0;
        padding: 0;
      }
      .nav-text:not(.selected):hover::after {
        background-color: gray;
      }
    }
  }
}

@media (max-width: 768px) {
  #destination {
    .destination-wrapper {
      .destination-body {
        display: flex;
        flex-direction: column;
        .left-side {
          img {
            width: 300px;
            height: 300px;
          }
        }
        .right-side {
          margin: 0 auto;
          text-align: center;
          .nav-wrapper {
            display: flex;
            justify-content: center;
            margin-top: 1rem;
          }
          .planet-info {
            justify-content: space-around;
            max-width: 40rem;
          }
        }
      }
    }
  }
}
@media (max-width: 375px) {
  #destination {
    .destination-wrapper {
      .destination-body {
        .left-side {
          img {
            width: 170px;
            height: 170px;
          }
        }

        .right-side {
          h2 {
            margin-top: 2rem;
          }
          .planet-info {
            flex-direction: column;
          }
        }
      }
    }
  }
}
</style>
