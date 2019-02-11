<template>
  <v-layout>
    <v-flex xs12 sm3 offset-sm3>
      <v-card height=380 width=280>
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
          aspect-ratio="1.5"
        >
        </v-img>

        <v-card-title class="justify-space-between" height=400 primary-title>
          <div class="titre">
            <h2> Céramique </h2>
          </div>
          <div class="ville">
            <h2> Bordeaux </h2>
          </div>
        </v-card-title>
          <v-card-title primary-title>  
            <div class="image_artisan">
            <img src="" alt="1"/>
          </div>
          <div class="mini_description">
            <ul class="list_description">
              <li> 20 euros </li>
              <li> Hans </li>
              <li> Etudiant à l'INP Enseihhtsdj </li>
              <li> 3 h </li>
            </ul>
          </div>
          </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
</template>


<script>
export default {
    name: "cardatelier",
    data() {
      return {
      //
      };
    }
}
</script>

<style scoped>

  v-card-title{
    overflow: hidden;
  }


  .flex.offset-sm3 {
    margin-left: 3%;
    }

  .image_artisan{
    margin-right: 20px;
    border-radius: 50%;
  }

  .mini_description{
    margin-left: 50px;
  }

  .list_description{
    text-align: left;
    list-style-position: inside;
    list-style: none;
    }​

  li {
    list-style: none;
   
  }

  ul {
    overflow:auto;

  }
</style>
