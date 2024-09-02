<template>
  <v-container>
        <h1 class="title">Get in touch</h1>

    <v-row justify="center">
      <v-col cols="12" md="6">
        <v-card>
          <v-card-title class="card-h1">Send me a message</v-card-title>
          <v-card-text>
            <v-form ref="contactForm" v-model="valid" @submit.prevent="submitForm">
              <v-text-field
                v-model="form.name"
                label="Name"
                :rules="[v => !!v || 'Name is required']"
                required
              ></v-text-field>

              <v-text-field
                v-model="form.email"
                label="Email"
                :rules="[v => !!v || 'Email is required', v => /.+@.+\..+/.test(v) || 'E-mail must be valid']"
                required
              ></v-text-field>

              <v-textarea
                v-model="form.message"
                label="Message"
                :rules="[v => !!v || 'Message is required']"
                required
              ></v-textarea>

              <v-btn
                :disabled="!valid"
                color="primary"
                @click="submitForm"
                class="mt-4"
              >
                Send Message
              </v-btn>
            </v-form>
          </v-card-text>
        </v-card>
      </v-col>
      
      <v-col cols="12" md="6">
        <v-card class="mb-4">
          <v-card-title class="card-h1">Location & Availability</v-card-title>
          <v-card-text>
            <p><strong>Location:</strong> São Paulo, Brazil</p>
            <p><strong>Availability:</strong> Monday to Friday, 9 AM - 6 PM (BRT)</p>
          </v-card-text>
        </v-card>

        <v-card class="mt-4">
          <v-card-title class="card-h1">Find Me</v-card-title>
          <v-card-text>
            <iframe
              width="100%"
              height="220"
              frameborder="0"
              style="border:0"
              allowfullscreen
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3656.5236338917177!2d-46.7285012850218!3d-23.574103184673185!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94cef88d26458b4d%3A0x55aaf38a7b29bc73!2sButant%C3%A3%2C%20S%C3%A3o%20Paulo%20-%20State%20of%20S%C3%A3o%20Paulo%2C%2005503-090%2C%20Brazil!5e0!3m2!1sen!2sus!4v1693329909876!5m2!1sen!2sus"
            ></iframe>
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
      valid: false,
      form: {
        name: '',
        email: '',
        message: ''
      }
    };
  },
  methods: {
    submitForm() {
      alert('Message sent successfully!');
      this.$refs.contactForm.reset();
    }
  }
}
</script>

<style scoped>
.title {
  padding: 18px;
  font-size: 42px;
  font-family: "Lora", serif;
  text-align: center;
  text-decoration: underline #FFEA00;
}
.card-h1 {
  font-size: 28px;
  font-family: "Lora", serif;
  text-align: center;
  margin-bottom: 16px;
}
.v-card {
  border-radius: 10px;
  transition: transform 0.3s, box-shadow 0.3s;
  border: 2px solid #FFEA00;
}
.v-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}
.v-btn {
  color: #FFEA00;
  transition: color 0.3s;
}
.v-btn:hover {
  color: #312d01;
}
</style>
