<template>
  <div>
    <h1 align="center">Let's talk!</h1>
  </div>
    <form @submit.prevent="submit">
      <v-text-field
        v-model="name.value.value"
        :counter="10"
        :error-messages="name.errorMessage.value"
        label="Name"
      ></v-text-field>

      <v-text-field
        v-model="email.value.value"
        :error-messages="email.errorMessage.value"
        label="E-mail"
      ></v-text-field>

      <v-text-field
        label="Message"
      ></v-text-field>
  
      <v-btn
        class="submit-btn"
        type="submit"
      >
        Submit
      </v-btn>
  
      <v-btn @click="handleReset"
      class="clear">
        Clear
      </v-btn>
    </form>
</template>  
<script setup>
  import { useField, useForm } from 'vee-validate'

  const { handleSubmit, handleReset } = useForm({
    validationSchema: {
      name (value) {
        if (value?.length >= 2) return true

        return 'Name needs to be at least 2 characters.'
      },
      email (value) {
        if (/^[a-z.-]+@[a-z.-]+\.[a-z]+$/i.test(value)) return true

        return 'Insert a valid e-mail.'
      }
    },
  })
  const name = useField('name')
  const email = useField('email')
  const submit = handleSubmit(values => {
    alert(JSON.stringify(values, null, 2))
  })
</script>
<style scoped>
form{
  padding: 40px;
}
h1{
  padding: 20px;
  font-size: 42px;
  font-family: "Lora", serif;
  text-decoration: underline #FFEA00;
}
.submit-btn{
  transform: scale(1);
  box-shadow: 0 2px 15px rgba(219, 187, 4, 0.5);
  border: 1.5px solid #FFEA00;
  border-radius: 10px;
  margin:10px;
  transition: all 0.3s ease; 
}

.submit-btn:hover {
  background-color: #FFEA00;
}
.clear{
  transform: scale(1);
  box-shadow: 0 2px 15px rgba(255, 0, 0, 0.664);
  border: 1.5px solid #ff0000;
  border-radius: 10px;
  transition: all 0.3s ease; 
}

.clear:hover {
  background-color: #ff0000;
}

</style>
