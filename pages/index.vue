<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">

      <v-sheet v-if="!items">
          <v-skeleton-loader
              :v-bind="attrs"
              type="card, actions"
          >
          </v-skeleton-loader>  
      </v-sheet>

      <dir-carousel-product :items="items" v-else-if="items"></dir-carousel-product>

      <dir-card-recommended 
        v-for="recom of recommended"
        :key="recom.id"
        :name="recom.nombre"
        :description="recom.descripcion"
        :imagen="recom.imagen"
      >
      </dir-card-recommended>
      
    </v-col>
  </v-row>
</template>

<script>

import CarouselProduct from '../components/CarouselProduct'
import CardRecommended from '../components/CardRecommended'
import axios from 'axios'

export default {
  head(){
    return{
      title: 'Demo-Vue | Index',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'WebView Demo'
        }
      ],
      htmlAttrs:{
        lang: 'en'
      }
    }
  },
  components: {
    'dir-carousel-product': CarouselProduct,
    'dir-card-recommended': CardRecommended
  },
  data(){
    return{
      id_rec: 2,
      items: null,
      recommended: null,
      attrs: {
        class: 'mb-6',
        boilerplate: true,
        elevation: 7,
      },
    }
  },
  // async created(){
  //   try {
  //     const res = await axios.get('https://aeb3tdj22j.execute-api.us-east-2.amazonaws.com/Prod/get-categories/')
  //     this.items = res.data.categorias
  //   } catch (error) {
  //     console.log(error);
  //   }
  // },
  async mounted(){
    try {
      const res = await axios.get('https://aeb3tdj22j.execute-api.us-east-2.amazonaws.com/Prod/get-categories/')
      this.items = res.data.categorias
    } catch (error) {
      console.log(error);
    }
  },
  created(){
    this.getRecommended()
  },
  methods:{
    async getRecommended(){
      try {
        const res = await axios.get('https://aeb3tdj22j.execute-api.us-east-2.amazonaws.com/Prod/get-categories/')
        this.recommended = res.data.categorias[1]
        console.log(this.recommended);
      } catch (error) {
        console.log(error);
      }
    }
  }
    
}
</script>
