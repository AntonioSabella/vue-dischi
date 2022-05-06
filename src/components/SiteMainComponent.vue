<template>
    <main class="container_fluid bg_main">
     <section  v-if='!loading'>
            <div class="container w-90">
            <div class="row row-cols-5 p-4 gy-4 h-100">
                <SongList :song= 'album' v-for="(album, index) in albums" :key="index"/>
       <!--         <div class="col d-flex align-items-center text-center h-100" v-for="(album, index) in albums" :key="index">
                    <div class="card bg_header p-3">
                        <img class="img-fluid" :src="album.poster" alt="">
                        <h6 class="text-white mt-3 lh-0">{{album.title}}</h6>
                        <p class="text-muted m-0">{{album.author}}</p>
                        <p class="text-muted m-0">{{album.year}}</p>
                    </div>
                </div> -->
            </div>
        </div>
    </section>
    <section v-else>
        <h2>...Caricamento pagina</h2>
    </section>
    </main>
</template>

<script>
import SongList from '@/components/SongListComponent.vue';
import axios from "axios"; 

export default {
     name: "SiteMainComponent",
     components: {
         SongList,
     },
     data () {
         return {
             link: "https://flynn.boolean.careers/exercises/api/array/music",
             albums: null,
             loading: true,
        };
     },
     methods: {
     },
     mounted() {
         console.log(axios);
          axios
         .get(this.link)
         .then((response) => {
             console.log(response);
             this.albums = response.data.response;
             this.loading = false;
         })
     }
 }


</script>

<style lang='scss' scoped>
    .container_fluid {
        height: calc(100% - 80px);
        h2 {
            text-align: center;
            color: white;
        }
    }

    img {
        aspect-ratio: 1 / 1;
    }

    .card {
        max-height: 400px;
    }

</style>