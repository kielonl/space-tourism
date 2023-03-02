<template>
  <main id="crew">
    <HeaderMenu />
    <div class="crew-wrapper">
      <div class="crew-heading--mobile">
        <h5>02</h5>
        <h5>MEET YOUR CREW</h5>
      </div>
      <div class="crew-body">
        <div class="left-side">
          <div class="crew-heading">
            <h5>02</h5>
            <h5>MEET YOUR CREW</h5>
          </div>
          <div>
            <h4>{{ crewInfo[currentCrew].title }}</h4>
            <h3>{{ crewInfo[currentCrew].name }}</h3>
          </div>
          <div class="body-text">
            {{ crewInfo[currentCrew].bodyText }}
          </div>
          <div class="slider">
            <input type="radio" value="douglasHurley" v-model="currentCrew" />
            <input
              type="radio"
              value="markShuttleworth"
              v-model="currentCrew"
            />
            <input type="radio" value="victorGlover" v-model="currentCrew" />
            <input type="radio" value="anoushehAnsari" v-model="currentCrew" />
          </div>
        </div>
        <div class="right-side">
          <img
            :src="crewInfo[currentCrew].image"
            :alt="crewInfo[currentCrew].name"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import HeaderMenu from "@/components/HeaderMenu.vue";
import { ref } from "vue";

interface Crew {
  [key: string]: {
    name: string;
    title: string;
    image: string;

    bodyText: string;
  };
}

const crewInfo: Crew = {
  douglasHurley: {
    name: "Douglas Hurley",
    title: "COMMANDER",
    image: "src/assets/crew/image-douglas-hurley.png",
    bodyText:
      "Douglas Gerald Hurley is an American engineer, former Marine Corps pilot and former NASA astronaut. He launched into space for the third time as commander of Crew Dragon Demo-2.",
  },
  markShuttleworth: {
    name: "Mark Shuttleworth",
    title: "MISSION SPECIALIST",
    image: "src/assets/crew/image-mark-shuttleworth.png",
    bodyText:
      "Mark Richard Shuttleworth is the founder and CEO of Canonical, the company behind the Linux-based Ubuntu operating system. Shuttleworth became the first South African to travel to space as a space tourist.",
  },
  victorGlover: {
    name: "Victor Glover",
    title: "PILOT",
    image: "src/assets/crew/image-victor-glover.png",
    bodyText:
      "Pilot on the first operational flight of the SpaceX Crew Dragon to the International Space Station. Glover is a commander in the U.S. Navy where he pilots an F/A-18.He was a crew member of Expedition 64, and served as a station systems flight engineer. ",
  },
  anoushehAnsari: {
    name: "Anousheh Ansari",
    title: "FLIGHT ENGINEER",
    image: "src/assets/crew/image-anousheh-ansari.png",
    bodyText:
      "Anousheh Ansari is an Iranian American engineer and co-founder of Prodea Systems. Ansari was the fourth self-funded space tourist, the first self-funded woman to fly to the ISS, and the first Iranian in space. ",
  },
};

const currentCrew = ref<
  "douglasHurley" | "markShuttleworth" | "victorGlover" | "anoushehAnsari"
>("douglasHurley");
</script>

<style scoped lang="scss">
input[type="radio"] {
  appearance: none;
  background: #fff;
  opacity: 0.175;
  margin: 0;
  font: inherit;
  color: currentColor;
  width: 1.15em;
  height: 1.15em;
  border: 0.15em solid currentColor;
  border-radius: 50%;
  cursor: pointer;
  &:hover {
    opacity: 0.5;
  }
  &:checked {
    opacity: 1;
  }
}

.slider {
  display: flex;
  flex-direction: row;
  align-self: end;
  gap: 0.5rem;
}

#crew {
  background: url("../assets/crew/background-crew-desktop.jpg") no-repeat center
    center fixed;
  background-size: cover;
  height: 100vh;
  overflow: hidden;

  .crew-wrapper {
    .crew-heading--mobile {
      display: none;
    }
    .crew-heading {
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
      h5 {
        margin-bottom: 0;
      }
    }
    .crew-body {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: 1fr;
      grid-column-gap: 0px;
      grid-row-gap: 0px;
      .left-side {
        z-index: 1;
        grid-area: 1 / 1 / 2 / 2;
        display: grid;
        transform: translate(25%, 0);
        h4 {
          margin-bottom: 1rem;
          opacity: 0.5;
        }
        h3 {
          margin: 0rem 0rem 2rem 0rem;
          text-transform: uppercase;
        }
        .body-text {
          max-width: 38rem;
          word-wrap: break-word;
        }
      }
      .right-side {
        grid-area: 1 / 2 / 2 / 3;
        display: flex;
        justify-content: center;

        img {
          z-index: 0;
          width: 33vmax;
          aspect-ratio: 0.81;

          position: fixed;
          bottom: 0;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .slider {
    justify-content: center;
    margin-top: 2rem;
  }
  #crew {
    background: url("../assets/crew/background-crew-tablet.jpg") no-repeat
      center center fixed;
    .crew-wrapper {
      .crew-heading {
        margin: 0 -3rem;
        h5 {
          margin-bottom: 0;
        }
      }
      .crew-body {
        display: flex;
        flex-direction: column;

        .left-side {
          transform: unset;
          justify-content: center;
          align-items: center;
          padding: 0 4rem;
          text-align: center;
        }
        .right-side {
          img {
            position: absolute;
            width: 270px;
          }
        }
      }
    }
  }
}

@media (max-width: 375px) {
  #crew {
    background: url("../assets/crew/background-crew-mobile.jpg") no-repeat
      center center fixed;
    .crew-wrapper {
      .crew-heading--mobile {
        width: 100%;
        display: flex;
        justify-content: center;
        flex-direction: row;
        margin: 0;
        margin-bottom: 1rem;
        gap: 1rem;
        & > h5:nth-child(1) {
          color: white;
          opacity: 0.2;
          font-weight: bold;
        }
        & > h5:nth-child(2) {
          color: white;
        }
        h5 {
          margin-bottom: 0;
        }
      }
      .crew-body {
        flex-direction: column-reverse;

        .right-side {
          border-bottom: 1px solid #383b4b;
          margin: 0 2rem;
          img {
            position: unset;
            height: 225px;
            width: 170px;
          }
        }

        .left-side {
          padding: 0;
          h4 {
            font-size: 16pt;
          }
          h3 {
            margin-bottom: 1rem;
          }
          .body-text {
            padding: 0 1rem;
          }
          div:nth-child(1) {
            order: 2;
            display: none;
          }
          div:nth-child(2) {
            order: 3;
          }
          div:nth-child(3) {
            order: 4;
          }
          div:nth-child(4) {
            order: 1;
          }
        }
      }
    }
  }
}
</style>
