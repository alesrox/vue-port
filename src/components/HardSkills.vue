<template>
    <div class="skillDiv">
        <div class="jumbotron">
            <center>
                <h1>Hard Skills</h1>
                <hr />
            </center>
            <center>
                <div v-bind:key="skill.name" v-for="skill in skills" class="skillsGroup">
                    <Popper arrow hover placement="top">
                        <img :src="skill.img" :alt="skill.name" class="skillImg">
                        <template #content>
                            <div>{{skill.name}}</div>
                        </template>
                    </Popper>
                </div>
            </center>
        </div>
    </div>
</template>

<script>
import Popper from "vue3-popper";
import axios from "axios";

export default {
    name: 'Skills',
    components: {
        Popper
    },
    data() {
        return {
            skills: null
        }
    },
    mounted() {
        axios.get("https://FunnyAdoredCoderesource.alexros.repl.co/skills").then((result) => {
            this.skills = result.data;
        })
    }
}
</script>


<style scoped>
:root {
    --popper-theme-background-color: #22303a;
    --popper-theme-padding: 20px;
    --popper-theme-text-color: #fff;
    --popper-theme-border-radius: 25px;
}

.skillDiv {
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    font-family: 'Mukta', sans-serif;
    box-sizing: unset;
    padding: 3em;
    background: #22303a;
}

.skillImg {
    width: 150px;
    cursor: pointer;
}

.skillsGroup {
    display: inline-block;
}

.jumbotron {
    margin: 40px;
    color: black;
    width: 100%;
}

h1 {
    margin: 0 0 0.5em 0;
    font-family: system-ui;
}

@media screen and (max-width: 451px) {
    .skillImg {
        width: 75px;
    }

    .jumbotron {
        margin: 5px;
    }
}

:deep(.popper) {
    background: #22303a !important;
    padding: 20px !important;
    border-radius: 20px !important;
    color: #fff !important;
    /* font-weight: bold; */
    /* text-transform: uppercase; */
}

:deep(.popper #arrow::before) {
    background: #22303a !important;
}

:deep(.popper:hover),
:deep(.popper:hover > #arrow::before) {
    background: #22303a !important;
}
</style>