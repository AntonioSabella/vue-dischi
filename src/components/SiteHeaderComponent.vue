<template>
   <header id="site_header" class="container_fluid bg_header d-flex justify-content-between">
        <div class="logo_box">
                <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/spotify-download-logo-30.png" alt="">   
        </div>
        <div class="d-flex">
            <label for="genere">Seleziona il tuo genere</label>
            <select @change='select' class="form-select bg_main w-100 h-50 text-white" aria-label="Default select example" name="genere" id="genere" v-model='select'>
                <option selected disabled>Generi Musicali</option>
                <option value="All">All</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
                <option value="Rock">Rock</option>
            </select>
        </div>

   
    </header> 
</template>

<script>
export default {
    name: 'SiteHeaderComponent',
    props: {

    },
    data () {
        return {
            selectedGenere : ''
        }
    },
    methods: {
        select() {
            console.log(this.select);
        }
    }
}
</script>

<style lang='scss' scoped>
 #site_header {
     height: 100px;
     padding: 0.5rem;
     label {
         color: white;
     }
 }

 .logo_box {
     padding: 0.5rem 1.5rem;
     img {
         width: 50px;
         aspect-ratio: 1/1;
     }
 }
</style>
