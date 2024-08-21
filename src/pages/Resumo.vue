<template>
  <v-container>
    <h1 align="center">Apresentation</h1>
    <v-row>
      <v-col cols="12" md="4">
        <v-card>
          <v-card-title>About me</v-card-title>
          <v-card-text>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus facilisis ligula quis ultrices fringilla. Integer dignissim, lectus quis scelerisque suscipit, tellus velit maximus est, sed rhoncus erat metus id lacus. Morbi vulputate, nisl vel ultrices faucibus, velit urna porta nisi, eget volutpat nunc nisl vel libero. Mauris vulputate porta velit. In aliquet lacinia neque, in imperdiet sapien auctor nec. Integer et lacinia ante, sed vestibulum urna. Nam sodales erat et efficitur tincidunt. Mauris lacinia quam ut scelerisque ultricies. Curabitur vitae scelerisque quam. Ut faucibus metus vel nisl auctor, vel tempor erat facilisis. Maecenas laoreet faucibus mauris non sagittis.
Duis tincidunt sed augue eu sodales. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Curabitur tincidunt odio mauris, vitae congue odio maximus quis. Aliquam vel ornare mauris. Maecenas non auctor libero.
            </p>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12" md="4">
        <v-card>
          <v-card-title>Skills</v-card-title>
          <v-card-text>
            <div v-for="skill in skills" :key="skill.name" class="skill">
              <p>{{ skill.name }} - {{ skill.value }}%</p>
              <v-progress-linear
                :value="skill.value"
                color="amber"
                height="10"
                :model-value= skill.value
                striped
              ></v-progress-linear>
            </div>
          </v-card-text>
          <v-card-title>Languages</v-card-title>
          <v-card-text>
            <div v-for="language in languages" :key="language.name" class="skill">
              <p>{{ language.name }} - {{ language.value }}%</p>
              <v-progress-linear
                :value="language.value"
                color="amber"
                height="10"
                :model-value= language.value
                striped
              ></v-progress-linear>
            </div>
          </v-card-text>
        </v-card>
      </v-col>
      <v-col cols="12" md="4">
        <v-card>
          <v-card-title>Resume</v-card-title>
          <v-card-text>
            <p>You can see and dowload my resume clicking in the button bellow: </p>
            <v-spacer></v-spacer>
            <v-btn 
              class="dowload-btn"
              @click="downloadResume">
              Dowload Resume
            </v-btn>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'Portfolio',
  data() {
    return {
      skills: [
        { name: 'Vue.js', value: 40 },
        { name: 'Vuetify', value: 50 },
        { name: 'JavaScript', value: 75 },
        { name: 'HTML & CSS', value: 95 },
        { name: 'UX/UI', value: 65 }
      ],
      languages: [
      { name: 'English', value: 70},
      { name: 'Spanish', value: 40},
      { name: 'Portuguese / Native', value: 100}
      ]
    };
  },
  methods: {
    downloadResume() {
      const link = document.createElement('a');
      link.href = '/path/to/your/resume.pdf';
      link.download = 'Curriculo.pdf';
      link.click();
    }
  }
}
</script>

<style scoped>
h1 {
  padding: 18px;
  font-size: 42px;
  font-family: "Lora", serif;
  text-decoration: underline #FFEA00;
}

.skill {
  margin-bottom: 20px;   
}
.dowload-btn{
  transform: scale(1);
  box-shadow: 0 2px 15px rgba(219, 187, 4, 0.5);
  border: 1.5px solid #FFEA00;
  border-radius: 10px;
  margin-top: 15px; 
  transition: all 0.3s ease; 
}

.dowload-btn:hover {
  background-color: #FFEA00;
}
</style>
