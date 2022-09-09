<template>
    <section>
        <h1>Certificates</h1>
        <div class="gallery">
            <div v-for="certificate in certificates" v-bind:key="certificate.name" style="width: 100%">
                <img :src="certificate.url" :alt="certificate.name" class="certificate">
            </div>
        </div>
    </section>
</template>

<script>
import axios from "axios";

export default {
    name: 'Certificates',
    data() {
        return {
            certificates: null
        }
    },
    mounted() {
        axios.get("https://FunnyAdoredCoderesource.alexros.repl.co/certificates").then((result) => {
            this.certificates = result.data;
        })
    }
}
</script>

<style scoped>
section {
    padding: 10px 40px;
    margin: 50px auto;
}

h1 {
    text-align: center;
    color: black;
    font-family: system-ui;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    grid-gap: 20px;
}

.certificate {
    display: block;
    margin: auto;
    cursor: pointer;
    width: 100%;
    height: 350px;
    border-radius: 8px;
}

@media screen and (max-width: 768px) {
    .gallery {
        grid-template-columns: repeat(auto-fit, minmax(275px, 1fr));
    }

    .certificate {
        height: 275px;
    }
}
</style>
