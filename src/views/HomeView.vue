<template>
  <div>
    <v-row class="ma-2">
      <v-col
        md="6"
        sm="12"
        cols="12"
        class="pa-3 d-flex flex-column"
        v-for="project in projects"
        :key="project.title"
      >
        <v-card class="elevation-5 flex d-flex flex-column">
          <v-card-title primary-title>
            <v-row>
              <v-col>
                <p class="headline mb-0">{{ project.title }}</p>
              </v-col>
              <v-col width="30%">
                <v-chip :color="`${project.status}`" :class="`v-chip--active white--text caption my-2`">{{project.status}}</v-chip>
              </v-col>
            </v-row>
          </v-card-title>

          <v-card-text class="flex">
            <div class="body-1">{{ project.desc }}</div>
            <v-divider light style="margin-top: 15px"></v-divider>
            <v-divider light></v-divider>
          </v-card-text>
          <v-card-text>
            <v-row pa-3>
              <v-col width="30%">
                <h4 class="text-black">Assigned to</h4>
              </v-col>
              <v-col width="70">
                <h4>{{ project.person }}</h4>
              </v-col>
            </v-row>
             <v-row pa-3>
              <v-col width="50%">
                <h4 class="text-black">Deadline</h4>
              </v-col>
              <v-col width="50%">
                <h4>{{ project.deadline }}</h4>
              </v-col>
            </v-row>
          </v-card-text>
        </v-card>
      </v-col>

    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          title: "Create Website",
          desc: "wordpress theme installation",
          person: "Syed Talal Jilani",
          deadline:'12 Aug 2022',
          status:'ongoing'
        },
        { title: "Create Software", desc: "use java applet", person: "Ahsan" ,deadline:'25 Aug 2022',status:'pending'},
        { title: "Create App", desc: "use Flutter ", person: "bilal",deadline:'1 Aug 2022',status:'overdue'},
        { title: "Create Database", desc: "use firebase database", person: "Maryam",deadline:'1 Aug 2022',status:'complete'},
      ],
    };
  },
};
</script>

<style>
.v-chip.ongoing{
background:orangered;
}
.v-chip.complete{
  background: green;
}
.v-chip.overdue{
  background: red;
}
.v-chip.pending{
  background: blueviolet;
}
</style>