<script>
import axios from 'axios';
import { state } from '../state';
import Project_card from './Project_card.vue';

export default {
    name: 'AppMain',
    data() {
        return {
            //base_api_url: 'http://127.0.0.1:8000',
            state,
            projects_endpoint: '/api/projects',
            projects: ''
        }

    },
    components: {
        Project_card
    },
    mounted() {
        const url = state.base_api_url + this.projects_endpoint
        axios
            .get(url)
            .then(resp => {

                this.projects = resp.data.results
                console.log(this.projects);
            })
            .catch(err => {
                console.error(err)
            })
    }
}

</script>

<template>
    <section>
        <div class="container">
            <div class="row">
                <h1>Projects</h1>
                <Project_card v-for="(project, index) in projects.data" :project="project">
                </Project_card>
            </div>
        </div>
    </section>

</template>

<style scoped>


.row{
    margin: 0 -1rem;
    
    
}

</style>