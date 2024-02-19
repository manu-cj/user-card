<template>
    <main id="user-list">
        <div class="cards" v-for="(userData, index) in userData" :key="index">
            <img :src="userData.picture.large" class="user-picture"/>
            <p class="name-user">{{userData.name.first}} {{userData.name.last}}</p>
            <p class="data-user">{{userData.location.city}}</p>
            <p class="data-user">{{userData.email}}</p>
            <p class="data-user">Age : {{userData.dob.age}}</p>
        </div>
    </main>
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
            axios.get('https://randomuser.me/api/?results=12&nat=fr')
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
<style scoped>
    #user-list {
        width: 90%;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        flex-wrap: wrap;
    }

    .cards {
        width: 26%;
        height: 400px;
        border: 2px orange solid;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-around;
        color: aliceblue;
        background: rgba(3, 20, 20, 0.637);
        border-radius: 16px;
        box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
        backdrop-filter: blur(6.4px);
        -webkit-backdrop-filter: blur(6.4px);
        border: 5px solid rgba(204, 123, 2, 0.781);
        margin-top: 50px;
        margin-bottom: 50px;
    }

    .user-picture {
        border-radius: 50%;
        border: 3px rgb(112, 155, 128) solid;
        margin-top: 30px;
    }

    .name-user {
        font-size: large;
        font-weight: bolder;
    }

    .data-user {
        width: 80%;
        height: 10%;
        border: 2px rgb(112, 155, 128) solid;
        border-radius: 7px;
        display: flex;
        align-content: center;
        align-items: center;
        justify-content: center;
    }

    .data-user:hover {
        background-color: rgba(204, 123, 2, 0.781);
        border: 2px rgb(112, 155, 128) solid;
        cursor: pointer;
    }
    @media all and (min-width: 550px) and (max-width: 1160px) {
        .cards {
            width: 30%;
            height: 400px;
        }

        .data-user {
            font-size: small;
        }
    }

    @media all and (min-width: 550px) and (max-width: 800px) {
        .data-user {
            font-size: xx-small;
        }
    }

    @media all and (orientation: portrait) {
        .cards {
            width: 60%;
            height: 400px;
        }

        .data-user {
            font-size: small;
        }
    }


</style>