<template>
    <div class="contenedor">
        <h1>Recent Projects</h1>
        <div class="carousel">
            <div class="carouselContainer">
                <button aria-label="Previous" class="btnPrev">
                    <i class="fas fa-chevron-left"></i>
                </button>
                <div class="carouselList">
                    <div v-bind:key="project.title" v-for="project in projects">
                        <center class="carouselElement">
                            <div class="card" style="width: 18rem;">
                                <center class="bg-img">
                                    <img :src="project.img" class="card-img-top" :alt="project.title">
                                </center>
                                <div class="card-body">
                                    <h5 class="card-title">{{project.title}}</h5>
                                    <p class="card-text">{{project.p}}</p>
                                    <a :href="project.github" target="_blank" rel="noopener noreferrer">
                                        <div class="btn-github">
                                            Github <span class="fa fa-github"></span>
                                        </div>
                                    </a>
                                    <a :href="project.link" target="_blank" rel="noopener noreferrer">
                                        <div class="btn-demo">
                                            <span class="fa fa-play"></span>
                                        </div>
                                    </a>
                                </div>
                            </div>
                        </center>
                    </div>
                </div>
                <button aria-label="Next" class="btnNext">
                    <i class="fas fa-chevron-right"></i>
                </button>
            </div>
            <div role="tablist" class="carouselDots" style="margin-top: 2em;"></div>
        </div>
    </div>
</template>

<script>
import axios from "axios";

export default {
    name: 'Carousel',
    data() {
        return {
            projects: null
        }
    },
    mounted() {
        axios.get("https://FunnyAdoredCoderesource.alexros.repl.co/proyects").then((result) => {
            this.projects = result.data;
        })

        const carouselSet = () => {
            new Glider(document.querySelector('.carouselList'), {
                slidesToShow: 1,
                slidesToScroll: 1,
                dots: '.carouselDots',
                arrows: {
                    prev: '.btnPrev',
                    next: '.btnNext'
                },
                responsive: [
                    {
                        breakpoint: 735,
                        settings: {
                            slidesToShow: 2,
                            slidesToScroll: 2
                        }
                    },
                    {
                        breakpoint: 970,
                        settings: {
                            slidesToShow: 3,
                            slidesToScroll: 3
                        }
                    }
                ]
            });
        }

        setTimeout(carouselSet, 900);
        // carouselSet()
    },
}
</script>

<style scoped>
* {
    box-sizing: border-box;
}

body {
    font-family: 'Montserrat', sans-serif;
    min-height: 100vh;
    display: flex;
    align-items: center;
}

.contenedor {
    max-width: 1200px;
    width: 90%;
    margin: 100px auto;
}

h1 {
    margin: 0 0 2em 0;
    font-family: system-ui;
}

/* --- --- CAROUSEL --- --- */
.carouselContainer {
    position: relative;
}

.btnPrev,
.btnNext {
    position: absolute;
    display: block;
    width: 30px;
    height: 30px;
    border: none;
    top: calc(50% - 35px);
    cursor: pointer;
    line-height: 30px;
    text-align: center;
    background: none;
    opacity: 50%;
}

.btnPrev:hover,
.btnNext:hover {
    opacity: 100%;
}

.btnPrev {
    left: -30px;
}

.btnNext {
    right: -30px;
}

.carouselList {
    overflow: hidden;
    
}

.card {
    border-radius: 10px;
}

.bg-img {
    background-color: #27383e;
    border-radius: 10px;
    overflow: hidden;
}

.card-img-top {
    object-fit: cover;
    border-radius: 10px;
    width: 100%; 
    height: 275px;
    transition: all 1.5s ease;
}

.bg-img:hover .card-img-top {
    cursor: pointer;
    transform: scale(1.25);
}

.btn-github {
    display: inline-block;
    padding: 0.4em 1em;
    border-radius: 4px;
    font-size: 16px;
    border: 1px solid #22303a;
    font-weight: bold;
    color: #22303a;
}


.btn-demo {
    display: inline-block;
    padding: 0.4em 1em;
    border-radius: 4px;
    margin-left: 1em;
    font-size: 16px;
    border: 1px solid #22303a;
    font-weight: bold;
    color: #22303a;
}

.btn-github:hover {
    text-decoration: none;
    color: #fff;
    background: #22303a;
}

.btn-demo:hover{
    text-decoration: none;
    color: #fff;
    background: #22303a;
}

@media screen and (max-width: 800px) {
    body {
        padding: 40px 0;
    }

    .btnPrev, .btnNext {
        margin: 20px;
    }
}
</style>