<template>
    <v-hover v-slot="{ hover }" open-delay="200">
        <v-card class="mx-auto" :elevation="hover ? 16:2" :class="{ 'on-hover' : hover }">
            <v-row>
                <v-col cols="2">
                    <v-img :src="imgPath" height="114px" width="114px"></v-img>
                </v-col> 
                <v-col class="ma-0 pa-0" cols="9">
                    <v-card-title>
                        {{title}}
                    </v-card-title>
                    <v-card-subtitle>
                        {{subTitle}}
                    </v-card-subtitle>          
                </v-col>
            </v-row>
        </v-card>
    </v-hover>
</template>

<script>
export default {
    name: 'CustomCard',
    data() {
        return {

        }
    },
    props: {
      title: '',
      subTitle: '',
      imgPath: ''
  }

}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@600&display=swap');

     .v-card {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 24px;
        background: #FFFFFF;
        box-shadow: 0px 4px 50px rgba(181, 213, 227, 0.5);
        backdrop-filter: blur(25px);
        border-radius: 20px;
    }
    

    .v-img{
        align-self: center;
    }
    .v-card-title{
        font-family: Open Sans;
        font-style: normal;
        font-weight: 600;
        font-size: 36px;
        line-height: 49px;
        /* identical to box height */
        text-align: left;
        letter-spacing: -0.04em;
        /* Dark */
        color: #173645;
    }
    .v-card-subtitle{
        font-family: Open Sans;
        font-style: normal;
        font-weight: 600;
        font-size: 36px;
        line-height: 49px;
        /* identical to box height */
        text-align: left;
        letter-spacing: -0.04em;
        /* Dark */
        color: #173645;
    }

    .v-card.on-hover.theme--dark{
        background-color: rgba(#FF0000, 1);
    }

    
    .v-img{
        contain: content;
    }

    .v-row {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    } 
</style>