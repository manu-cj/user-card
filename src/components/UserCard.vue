<template>
    <div v-for="(userData, index) in userData" :key="index">{{userData.gender}}</div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return {
            userData: [],
        }

    },

    methods: {
        getDataUser() {
            axios.get('https://randomuser.me/api/?results=3')
                .then(response=> {
                    this.userData = response.data.results
                    console.log(response.data.results)
                })
                    // en cas de réussite de la requête
                .catch(function (error) {
                    // en cas d’échec de la requête
               
                    console.log(error);
                });
        }
    },

    mounted() {
        this.getDataUser()

    }

}
</script>