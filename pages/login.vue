<template>
    <v-row align="center" justify="center">
        <v-col>
            <login-button></login-button>
        </v-col>
        
    </v-row>
</template>

<script>
import LoginButton from '../components/LoginButton.vue'
export default {
  components: { LoginButton },
}
</script>
