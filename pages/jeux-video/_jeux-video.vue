<template>
    <div>
        <h1>{{jeux.post_title}}</h1>
    </div>
    
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return{
            jeux: []
        }
    },
    mounted() {
        let nbr = this.$route.params.jeu;
        console.log(this.$route.params);
        axios.get('http://sitetest.local/wp-json/wp/v2/jeux_video').then(response => {
            this.jeux = response.data[nbr];console.log(this.jeux)
            });
        console.log(nbr);
    }
}
</script>