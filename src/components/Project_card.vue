<script>
import { state } from '../state';

export default {
    name: 'Project_card',
    data() {
        return {
            state
        }
    },
    props: {
        project: Object
    }
}

</script>
<template>
    <div class="card col-3">
        <div v-if="project.cover_image">
            <img :src="project.cover_image.startsWith('https://') ? project.cover_image : state.base_api_url + '/storage/' + project.cover_image"
                class="card-img-top" alt="">
        </div>
        <div v-else>
            <img class="w-100"
                src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/cc19044d-e9ea-4127-8248-20b8255cffce/d1h56v0-51ab4a21-5caa-449d-aa4c-6965c8692a16.jpg/v1/fill/w_333,h_493,q_75,strp/teo4_cards_13__error_404_by_theevilone4_d1h56v0-fullview.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9NDkzIiwicGF0aCI6IlwvZlwvY2MxOTA0NGQtZTllYS00MTI3LTgyNDgtMjBiODI1NWNmZmNlXC9kMWg1NnYwLTUxYWI0YTIxLTVjYWEtNDQ5ZC1hYTRjLTY5NjVjODY5MmExNi5qcGciLCJ3aWR0aCI6Ijw9MzMzIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.5PUnmK0Rkx8mLPs_PIdRr8FuvtEUHRavaDfPkhV36S0"alt="">
        </div>
        <div class="card-body">
            <h5 class="card-title">{{ project.name }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
    </div>


</template>
<style scoped>

.col-3 {
    width: calc((100%/10)*3  - 2rem);
    margin: 1rem;
}

</style>