<!-- <script>
import axios from "axios";
import { BASE_URL } from "../data/data";
import { store } from "../data/store";

export default {
    name: "Date",
};
</script>

<template>
    <div class="container-fluid">
        <h1 class="text-center p-3">Concerti</h1>
        <table class="table table-dark table-striped table-hover">
            <thead>
                <tr>
                    <th scope="col">Luogo</th>
                    <th scope="col">Data</th>
                    <th scope="col">Descrizione</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>
                        Blue turtle: Passeggiata Colonna, P.za Amedeo, 16c,
                        80121 Napoli NA
                    </td>
                    <td>8 Marzo</td>
                    <td>Gypsy jazz duo</td>
                </tr>
                <tr>
                    <td>Versa: Via Mezzocannone, 103, 80134 Napoli NA</td>
                    <td>9 Marzo</td>
                    <td>Gypsy jazz duo</td>
                </tr>
                <tr>
                    <td>Via Guglielmo Marconi 8/19, Angri SA</td>
                    <td>22 Marzo</td>
                    <td>Araputo Zen</td>
                </tr>
                <tr>
                    <td>
                        Auditorium di bagnoli: Via Diocleziano, 341, 80124
                        Napoli NA
                    </td>
                    <td>25 Marzo</td>
                    <td>
                        OEOAS (orchestra elettroacustica officina arti sonore)
                    </td>
                </tr>
                <tr>
                    <td>
                        Auditorium novecento: Via Enrico De Marinis, 4, 80134
                        Napoli NA
                    </td>
                    <td>11 Aprile</td>
                    <td>Alfredo Pumilia ensemble, presentazione Miradöis</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<style lang="scss" scoped>
.container-fluid {
    color: white;
    height: 100vh;
    background-image: url("../assets/violinome.jpg");
    background-size: cover;
}
</style>
 -->

<template>
    <div class="container-fluid">
        <h1 class="text-center p-3">Concerti</h1>
        <table class="table table-dark table-striped table-hover">
            <thead>
                <tr>
                    <th scope="col">Luogo</th>
                    <th scope="col">Data</th>
                    <th scope="col">Descrizione</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="post in posts" :key="post.id">
                    <td>{{ post.title }}</td>
                    <td>{{ post.date }}</td>
                    <td v-html="post.text"></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
import axios from "axios";
import { BASE_URL } from "../data/data";
import { store } from "../data/store";

export default {
    name: "Date",
    data() {
        return {
            posts: []
        };
    },
    mounted() {
        this.fetchPosts();
    },
    methods: {
        async fetchPosts() {
            try {
                const response = await axios.get(`${BASE_URL}/json`);
                this.posts = response.data;
            } catch (error) {
                console.error("Errore durante il recupero dei post:", error);
            }
        }
    }
};
</script>

<style lang="scss" scoped>
.container-fluid {
    color: white;
    height: 100vh;
    background-image: url("../assets/notte.jpg");
    background-size: cover;
}
</style>