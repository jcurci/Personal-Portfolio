<template>
    <div>
        <h1 class="title" align="center">My Projects</h1>
      <v-row justify="center">
        <v-col cols="12" sm="12" md="4" v-for="project in projects" :key="project.title">
          <v-card class="project-card" elevation="3">
            <v-img :src="project.image" height="120px" :class="{ 'hover-image': hover }"></v-img>
            <v-card-title class="card-title">{{ project.title }}</v-card-title>
            <v-card-text class="card-text">{{ project.description }}</v-card-text>
            <v-card-actions>
              <v-btn :href="project.link" target="_blank" class="project-btn">View {{ project.title }}</v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        hover: false,
        projects: [
          {
            title: 'Cripto-Manager',
            description: 'Cripto Manager under construction.',
            image: '',
            link: 'https://github.com/username/project1'
          },
          {
            title: 'Climate APP',
            description: 'Climate APP under construction.',
            image: '',
            link: 'https://github.com/username/project2'
          },
          {
            title: 'Bikcraft',
            description: 'E-commerce with HTML | CSS | JS.',
            image: 'https://www.origamid.com/wp-content/themes/origamid_theme/img/page/projetos/bikcraft.jpg',
            link: 'https://jcurci.github.io/bikcraft/',
          },
          {
            title: 'To-do list',
            description: 'To-do list under construction.',
            image: '',
            link: 'https://github.com/username/project4'
          },
          {
            title: 'Project 5',
            description: 'Card reserved for project 5.',
            image: '',
            link: 'https://github.com/username/project5'
          },
          {
            title: 'Project 6',
            description: 'Card reserved for project 6.',
            image: '',
            link: 'https://github.com/username/project6'
          },
        ],
      };
    },
  };
  </script>
  
  <style scoped>
  .title {
    padding: 28px;
    font-size: 42px; 
    font-family: "Lora", serif;
    text-decoration: underline #FFEA00;
  }
  
  .project-card {
    border-radius: 10px;
    transition: transform 0.5s, box-shadow 0.2s;
    margin: 0 15px;
  }
  
  .project-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 15px rgba(0, 0, 0, 0.1);
    border: 2.5px solid #FFEA00;
    
  }
  
  .card-title {
    font-size: 18px;
    font-weight: bold;
    color: #222;
  }
  
  .card-text {
    font-size: 14px;
    color: #f7f7f7;
  }
  
  .project-btn {
    background-color: #FFC107;
    color: #000;
    width: 100%;
    text-transform: none;
    font-weight: bold;
  }
  
  .project-btn:hover {
    background-color: #FFEA00;
  }
  
  .hover-image {
    filter: brightness(0.95);
    border-radius: 8px 8px 0 0;
  }
  </style>
  