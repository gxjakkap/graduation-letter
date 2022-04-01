<template class="bg-slate-300">
    <body class="bg-slate-300 w-full h-screen overflow-y-auto">
      <div>
          <div>
            <h1 class="text-center text-stone-900 mb-4 text-3xl"><br>grad letter</h1>
          </div>
          <div class="text-center">
            <nuxt-img :src="Data.imagelink" class="ml-auto mr-auto mb-3 h-1/6 object-scale-down"></nuxt-img>
          </div>
          <h1 class="text-center text-stone-900 text-xl font-mali">
            <b>To:</b> @{{Data.usrname}} ({{Data.name}})
          </h1>
          <br>
          <div class="text-center ml-auto mr-auto w-5/6">
            <p class="text-center text-stone-900 text-lg font-mali">
              {{Data.paragraph}}
            </p>
            <p class="text-center text-stone-900 text-lg font-mali" v-if="Data.pr2">
              <br>
              {{Data.pr2}}
            </p>
            <p class="text-center text-stone-900 text-lg font-mali" v-if="Data.pr3">
              <br>
              {{Data.pr3}}
          </p>
          </div>
          <div v-if="Data.songid" class="text-center ml-auto mr-auto">
            <br>
            <p class="text-center text-stone-900 text-xl font-mali">Some (maybe or maybe not)random song for you :p</p>
            <iframe 
              style="border-radius:12px" 
              :src="getSongUrl()"
              class="ml-auto mr-auto mt-2"
              width="30%" 
              height="80" 
              frameBorder="0" 
              allowfullscreen="" 
              allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture">
            </iframe>
          </div>
          <br>
          <br>
          <p class="text-center text-stone-900 text-xl font-mali"><b>signature</b></p>
          <br>
          <p class="text-center text-xl font-mali">I'll be here</p>
          <p class="text-center text-lg underline text-cyan-600 hover:text-cyan-500 font-mali"><a href="https://instagram.com/" target="_blank">Instagram</a></p>  
          <p class="text-center text-lg underline text-cyan-600 hover:text-cyan-500 font-mali"><a href="https://facebook.com/" target="_blank">Facebook</a></p>
          <p class="text-center text-lg underline text-cyan-600 hover:text-cyan-500 font-mali"><a href="https://www.example.com" target="_blank">Website</a></p>
          <br>
          <br>
          <br>
          <p class="text-center text-stone-900 text-base underline hover:text-cyan-600"><a href="https://github.com/gxjakkap/graduation-letter" target="_blank">GuntxJakka © 2022</a> </p>
      </div>
    </body>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Mali&display=swap');
</style>

<script>
import Vue from 'vue'
import data from '~/static/data.json'

export default Vue.extend({
  async asyncData({ params }) {
    const Data = (data).find(
      (p) => p.slug === params.slug
    )
    return {
      Data,
    }
  },
  head (){
    return {
      title: `${this.Data.usrname}'s graduation letter`
    }
  },
  data: () => ({
    Data: {},
  }),
  methods:{
    getSongUrl(){
      return `https://open.spotify.com/embed/track/${this.Data.songid}`
    }
  }
})
</script>


