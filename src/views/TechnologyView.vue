<template>
  <main id="technology">
    <HeaderMenu />
    <div class="technology-wrapper">
      <div class="technology-heading">
        <h5>03</h5>
        <h5>SPACE LAUNCH 101</h5>
      </div>
      <div class="technology-body">
        <div class="left-side">
          <div class="left-container">
            <div class="slider">
              <div class="radio-container">
                <input
                  type="radio"
                  value="launchVehicle"
                  name="technology"
                  v-model="currentTechnology"
                />
                <label for="technology">1</label>
              </div>
              <div class="radio-container">
                <input
                  type="radio"
                  value="spacePort"
                  name="technology"
                  v-model="currentTechnology"
                />
                <label for="technology">2</label>
              </div>
              <div class="radio-container">
                <input
                  type="radio"
                  value="spaceCapsule"
                  name="technology"
                  v-model="currentTechnology"
                />
                <label for="technology">3</label>
              </div>
            </div>
            <div class="description">
              <div class="nav-text">THE TERMINOLOGY ...</div>
              <h3>{{ technologyInfo[currentTechnology].name }}</h3>
              <div class="body-text">
                {{ technologyInfo[currentTechnology].bodyText }}
              </div>
            </div>
          </div>
        </div>
        <div class="right-side">
          <div
            class="technology-image--portrait"
            :style="{
              background: `url(${technologyInfo[currentTechnology].image.portrait})`,
              backgroundSize: 'cover',
            }"
          ></div>
          <div
            class="technology-image--landscape"
            :style="{
              background: `url(${technologyInfo[currentTechnology].image.landscape})`,
              backgroundSize: 'cover',
            }"
          ></div>
        </div>
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import HeaderMenu from "@/components/HeaderMenu.vue";
import { ref } from "vue";

const technologyInfo = {
  launchVehicle: {
    name: "Launch Vehicle",
    bodyText:
      "A launch vehicle or carrier rocket is a rocket-propelled vehicle used to carry a payload from Earth's surface to space, usually to Earth orbit or beyond. Our WEB-X carrier rocket is the most powerful in operation. Standing 150 metres tall, it's quite an awe-inspiring sight on the launch pad!",
    image: {
      portrait: "src/assets/technology/image-launch-vehicle-portrait.jpg",
      landscape: "src/assets/technology/image-launch-vehicle-landscape.jpg",
    },
  },
  spacePort: {
    name: "Space Port",
    bodyText:
      "A spaceport or cosmodrome is a site for launching (or receiving) spacecraft, by analogy to the seaport for ships or airport for aircraft. Based in the famous Cape Canaveral, our spaceport is ideally situated to take advantage of the Earth’s rotation for launch.",
    image: {
      portrait: "src/assets/technology/image-spaceport-portrait.jpg",
      landscape: "src/assets/technology/image-spaceport-landscape.jpg",
    },
  },
  spaceCapsule: {
    name: "Space Capsule",
    bodyText:
      "A space capsule is an often-crewed spacecraft that uses a blunt-body reentry capsule to reenter the Earth's atmosphere without wings. Our capsule is where you'll spend your time during the flight. It includes a space gym, cinema, and plenty of other activities to keep you entertained.",
    image: {
      portrait: "src/assets/technology/image-space-capsule-portrait.jpg",
      landscape: "src/assets/technology/image-space-capsule-landscape.jpg",
    },
  },
};

const currentTechnology = ref<"launchVehicle" | "spacePort" | "spaceCapsule">(
  "launchVehicle"
);
</script>

<style scoped lang="scss">
.radio-container {
  position: relative;
  input[type="radio"] {
    appearance: none;
    background: transparent;
    margin: 0;
    font: inherit;
    width: 5em;
    height: 5em;
    border: 1px solid rgba(255, 255, 255, 0.25);
    border-radius: 50%;
    cursor: pointer;
    &:not(:checked):hover {
      border-color: white;
    }
    &:checked {
      background: white;
    }
    &:checked + label {
      color: black;
      z-index: 1;
    }
  }
  label {
    color: white;
    position: absolute;
    top: 20%;
    left: 39%;
    font-size: 32pt;
    margin: 0 auto;
    z-index: -1;
    cursor: pointer;
  }
}

#technology {
  background: url("src/assets/technology/background-technology-desktop.jpg")
    no-repeat center center fixed;
  background-size: cover;
  height: 100vh;
  overflow: hidden;
  .technology-wrapper {
    .technology-heading {
      display: flex;
      flex-direction: row;
      gap: 1rem;
      width: fit-content;
      & > h5 {
        font-size: 28px;
      }
      & > h5:nth-child(1) {
        color: white;
        opacity: 0.2;
        font-weight: bold;
      }
      & > h5:nth-child(2) {
        color: white;
      }
    }
    .technology-body {
      display: grid;
      grid-template-columns: 2fr 1fr;
      grid-template-rows: 1fr;
      grid-column-gap: 0px;
      grid-row-gap: 0px;
      .left-side {
        z-index: 1;
        transform: translateY(10rem);
        margin-bottom: 20rem;
        .description {
          .nav-text {
            color: #d0d6f9;
          }
        }
        .left-container {
          display: flex;
          flex-direction: row;
          justify-content: space-evenly;
          .slider {
            display: flex;
            flex-direction: column;
            align-self: center;
            gap: 1rem;
          }
        }

        h3 {
          margin: 0rem;
          text-transform: uppercase;
        }
        .body-text {
          max-width: 38rem;
          word-wrap: break-word;
          line-height: 32px;
          font-size: 18px;
        }
      }
      .right-side {
        width: 100%;
        height: 100%;
        .technology-image--portrait {
          background-size: cover;
          height: 100%;
        }
        .technology-image--landscape {
          display: none;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .radio-container {
    input[type="radio"] {
      width: 3.7em;
      height: 3.7em;
    }
    label {
      font-size: 24pt;
    }
  }
  #technology {
    background: url("src/assets/technology/background-technology-tablet.jpg")
      no-repeat center center fixed;
    .technology-wrapper {
      .technology-body {
        display: flex;
        flex-direction: column-reverse;
        .left-side {
          transform: translateY(0rem);
          margin-bottom: 0rem;
          .left-container {
            flex-direction: column;
            align-items: center;
            text-align: center;
            .slider {
              flex-direction: row;
              margin: 2rem 0;
            }
          }
        }
        .right-side {
          .technology-image--landscape {
            display: block;
            //background: url("src/assets/technology/image-launch-vehicle-landscape.jpg");
            background-position: center;
            height: 30vh;
          }
          .technology-image--portrait {
            display: none;
          }
        }
      }
    }
  }
  @media (max-width: 375px) {
    .radio-container {
      input[type="radio"] {
        width: 2.5em;
        height: 2.5em;
      }
      label {
        font-size: 16pt;
      }
    }
    #technology {
      background: url("src/assets/technology/background-technology-mobile.jpg")
        no-repeat center center fixed;
      .technology-wrapper {
        .technology-heading {
          width: 100%;
          justify-content: center;
          align-items: center;
          & > h5 {
            font-size: 16px;
          }
        }
        .technology-body {
          .left-side {
            .nav-text {
              font-size: 14px;
              margin-bottom: 1rem;
            }
            .left-container {
              .slider {
                margin: 1rem 0;
              }
            }
          }
          .description {
            padding: 0 1rem;
            h3 {
              font-size: 24px;
            }
            .body-text {
              font-size: 15px;
            }
          }
        }
      }
    }
  }
}
</style>
