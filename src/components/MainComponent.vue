<script>
import axios from 'axios';

export default{
    data(){
        return{
            projects: []
        }
    },
    created(){
        axios
        .get('http://127.0.0.1:8000/api/projects')
        .then(res => {
           //console.log(res.data); 

           this.projects = res.data.results.data;
            console.log(this.projects); 
        });
    }
};
</script>


<template>
    <main>
        <h1>
            Tutti i project
        </h1>

        <div class="project-container">
            <div v-for="project in projects" :key="project.id">
                <h2>
                    {{ project.title }}
                </h2>
                <h4 v-if="project.type !=null">
                    Type {{ project.type.title }}
                </h4>
                <div>
                    Tecnologie: 
                        <span v-for="technology in project.technologies">
                            {{ technology.title }}
                        </span>
                </div>
            </div>
        </div>

    </main>
</template>



<style scoped>
.project-container{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

.project-container > *{
    width: 30%;
    padding: 10px;
    border: 4px dashed blue;
}

h2, h1, h4{
    margin-bottom: 20px;
}

</style>