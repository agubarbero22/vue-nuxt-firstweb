<template>
  <v-form ref="login_form" v-model="valid" lazy-validation>
    <v-text-field v-model="name" :counter="10" :rules="nameRules" label="Name" required></v-text-field>
    <v-text-field v-model="password" :rules="passwordRules" label="Password" required></v-text-field>

    <v-select v-model="select" :items="items" :rules="[v => !!v ||'Item is required']" label="Item" required></v-select>

    <v-checkbox v-model="checkbox" :rules="[v => !!v || 'You must agree to continue!']" label="Do you agree?" required></v-checkbox>

    <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">Login</v-btn>
    <v-btn color="error" class="mr-4" @click="reset">Reset Form</v-btn>

    <v-btn color="warning" @click="resetValidation">Reset Validation</v-btn>
  </v-form>
</template>

<script>
    export default{
      data() {
        return {
          valid: true,
          name: '',
          nameRules: [
            v => !!v || 'Name is required',
            v => (v && v.length <= 10) || 'Name must be less than 10 characters',
          ],
          password: '',
          passwordRules: [
            v => !!v || 'Password is required',
            v => (v && v.length >= 8) || 'Password must be more than 8 characters',
            v => (v && v.length <= 12) || 'Password must be less than 12 characters'
          ],
          select: null,
          items:[
            'Item 1',
            'Item 2', 
            'Item 3',
            'Item 4',
          ],
          checkbox: false,
        }
      },

      methods: {
        validate() {
          let validation = this.$refs.login_form.validate();
          if(validation){
            alert('¡Los datos son correctos!');
          }else{
            alert('¡Los datos son incorrectos!');
          }
          
          
        },
        reset () {
          this.$refs.login_form.reset()
        },
        resetValidation(){
          this.$refs.login_form.resetValidation()
        },
      },
    }
</script>