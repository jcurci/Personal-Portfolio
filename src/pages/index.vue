<template>
  <v-container id="welcomeMsg">
    <div
      class="offset-md-1"
      data-aos="fade-in"
      data-aos-offset="1"
      data-aos-duration="800"
      data-aos-easing="ease-in-out"
      data-aos-once="true"
    >
      <v-col cols="12" md="6" xs="10">
        <img
          src=""
          style="position: right; aspect-ratio: 1.6; object-fit: contain; background: linear-gradient(to top right, rgba(0,0,0,.15), rgba(0,0,0,.7));"
        />
        <div id="textbox">
          <div>
            <h2 id="typeWriter">
              Hello World, Welcome!
              <div id="border"></div>
            </h2>
          </div>
          <h1>My name is Jhonatan Curci.</h1>
          <h2>
            I am a <span id="highlight">Web Developer</span>
            actually working on <a class="highlight-btn" href="https://www.mdsgroup.com.br/pt/" target="_blank">MDS BRASIL.</a>
          </h2>
        </div>
      </v-col>
      <v-btn 
        class="about-btn"
        to="/resumo"
      >About me</v-btn>
    </div>
  </v-container>
</template>

<style scoped>
#welcomeMsg h1,
h2 {
  color: #ffffff;
  letter-spacing: 2px;
  line-height: 32px;
  font-family: "Lora", serif;
}
.highlight-btn {
  color: #FFEA00;
}
#welcomeMsg h1 {
  font-size: 30px;
  font-weight: 400;
  cursor: default;
  line-height: 2;
}
#welcomeMsg h2 {
  font-size: 18px;
  font-weight: 300;
  cursor: default;
}
#textbox {
  margin-top: 80px;
}

.about-btn{
  transform: scale(1);
  box-shadow: 0 2px 15px rgba(219, 187, 4, 0.5);
  border: 1.5px solid #FFEA00;
  border-radius: 10px;
  margin-left: 10px; 
  transition: all 0.3s ease; 
}

.about-btn:hover {
  background-color: #FFEA00;
}

#typeWriter {
  height: 40px;
  white-space: nowrap;
  overflow: hidden;
  position: relative;
  animation: animated-text 2s steps(25, end) 1s 1 normal both;
}
#border {
  border-bottom: solid 3px #FFEA00;
  position: absolute;
  right: -7px;
  width: 20px;
  animation: animated-cursor 1050ms steps(25, end) infinite;
}
#highlight {
  box-shadow: inset 0 -7px 0 #ffea0436;
}
@keyframes animated-text {
  from {
    width: 0;
  }
  to {
    width: 209px;
  }
}
@keyframes animated-cursor {
  from {
    border-bottom-color: #FFEA00;
  }
  to {
    border-bottom-color: transparent;
  }
}
</style>
