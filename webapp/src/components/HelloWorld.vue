<template>
  <v-container>
    <v-row class="text-center mt-10">
      <v-col v-for="project in projects":key="project.weekNumber" class="col-xs-12 col-sm-6 col-md-6 col-lg-4" align="center">
          <v-card height="300" width="500" :class="{ avb: !project.available,}">
            <v-card-title>
              {{ project.name }}
              <v-spacer></v-spacer>
              <v-btn
                  :color="'#'+(Math.random()*0x66FFFF<<0).toString(16)"
                  dark
                  fab
                  small
                  style="opacity: 0.4"
              >
                <span class="subtitle-1">{{ project.weekNumber }}</span>
              </v-btn>
            </v-card-title>
              <v-layout justify-center>
                <v-card-text>
                  <p v-if="project.available" class="caption">{{ project.intro }}</p>
                  <p v-if="!project.available" class="caption">not available yet</p>
                </v-card-text>
              </v-layout>
            <v-layout>
              <v-card-actions class="card-actions" v-if="project.available">
                <v-spacer></v-spacer>
                  <v-btn class="indigo lighten-5 ml-2 mr-2" :href="project.githubUrl" target="_blank" small v-if="project.githubUrl">
                    <v-icon class="mr-2">mdi-github</v-icon>
                    Github
                  </v-btn>
                  <v-btn class="teal lighten-5 ml-2 mr-2" :href="project.liveUrl" target="_blank" small v-if="project.liveUrl">
                    <v-icon class="mr-2">mdi-web</v-icon>
                    Live
                  </v-btn>
                  <v-btn class="amber lighten-5 ml-2 mr-2" small>
                    <v-icon class="mr-2">mdi-dots-horizontal</v-icon>
                    Mehr
                  </v-btn>
                <v-spacer></v-spacer>
              </v-card-actions>
            </v-layout>
          </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      projects: [
        {
          name:"oneWeek",
          intro: "oneWeek, is my personal portfolio where i try to publish every week a programming project where i try to focus on one spcific topic.",
          description: "full bla blaa",
          weekNumber: 1,
          available: true,
          tags: ["vue", "vuex", "vuetify"],
          githubUrl: "https://github.com/dev-ale/oneWeek",
          liveUrl: false
        },
        {
          name:"Glassmorphism Calculator",
          intro: "blablabla",
          description: "full bla blaa",
          weekNumber: 2,
          available: true,
          tags: ["javascript", "css"],
          githubUrl: "https://github.com/dev-ale/calculator-glassmorphism",
          liveUrl: "https://glassmorphismcalc.surge.sh/"
        },
        {
          name:"fhnw iot lossprevention",
          intro: "blablabla",
          description: "full bla blaa",
          weekNumber: 3,
          available: true,
          tags: ["vue", "iot", "c++", "nodered", "mqtt"],
          githubUrl: "https://github.com/dev-ale/fhnw-iot-lossprevention",
          liveUrl: "https://lossprevention.surge.sh"
        },
        {
          name:"iot Bricks Gateways Frontend",
          intro: "blablabla",
          description: "full bla blaa",
          weekNumber: 4,
          available: true,
          tags: ["vue", "iot", "c++", "nodered", "mqtt"],
          githubUrl: "https://github.com/dev-ale/fhnw-iot-lossprevention",
          liveUrl: "https://iot-bricks.surge.sh"
        },
        {
          name:"Pomodoro Timer",
          intro: "blablabla",
          description: "full bla blaa",
          weekNumber: 5,
          available: false,
          tags: ["vue"],
          githubUrl: "https://github.com/dev-ale/pomodoro-timer-app",
          liveUrl: false
        },
        {
          name:"FHNW Vue SVG Animation",
          intro: "blablabla",
          description: "full bla blaa",
          weekNumber: 6,
          available: false,
          tags: ["vue"],
          githubUrl: "https://github.com/dev-ale/pomodoro-timer-app",
          liveUrl: false
        }
      ],
      mycolor: '#'+(Math.random()*0xFFFFFF<<0).toString(16)
    }),
    mounted() {

    },
    methods: {

    }
  }
</script>

<style>
  .card-actions {
    position: absolute;
    bottom: 0;
    align-items: center;
    justify-content: center;
  }
  .avb {
    opacity: 30%;
  }
</style>
