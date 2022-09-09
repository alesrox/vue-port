<template>
    <div class="bannerDiv">
        <div class="infoBanner">
            <h1 class="titleBanner">
                Alex Ros
                <div class="resumeBanner">My specialties are Python and Back-end Dev.</div>
            </h1>
            <div class="textBanner">
                I'm a {{ age }} years old spaniard boy who loves code. <br />
                I started to learn coding more than {{ experience }} years ago with Python and Web Back-end development.
                I'm always learning and improving.
            </div>
            <div class="socialButtons">
                <a href="https://twitter.com/alesrox" target="_blank" rel="noopener noreferrer">
                    <div class="btn-left">Twitter <span class="fa fa-twitter"></span></div>
                </a>
                <a href="https://www.instagram.com/aleesrox/" target="_blank" rel="noopener noreferrer">
                    <div class="btn-center">Instagram <span class="fa fa-instagram"></span></div>
                </a>
                <a href="https://github.com/alesrox" target="_blank" rel="noopener noreferrer">
                    <div class="btn-right">Github <span class="fa fa-github"></span></div>
                </a>
            </div>
        </div>
        <div class="imageBanner">
            <img src="https://dl.airtable.com/.attachmentThumbnails/dfdf7c82fb1541f0d5c6ed1e3e80afa1/00245e2f"
                alt="Alex Ros"
                style="cursor:pointer;" 
            >
        </div>
    </div>
</template>

<script>
export default {
    name: 'BannerFolio',
    data() {
        return {
            age: null,
            experience: null
        }
    },
    mounted() {
        let ageM = new Date().getMonth() + 1;
        if (ageM >= 8) {
            this.age = new Date().getFullYear() - 2005
        } else {
            this.age = new Date().getFullYear() - 2006
        }

        this.experience = new Date().getFullYear() - 2017
    }
}
</script>

<style scoped>
.bannerDiv {
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

@font-face {
    font-family: Kanitalic;
    font-style: bold;
    src: url(../fonts/Kanit-regular.ttf);
}

.infoBanner {
    padding: 1em;
    font-family: Kanitalic;
    text-align: left;
    margin: 0 1em;
}

.titleBanner {
    text-shadow: 0.2px 0.5px 0.2px white;
    font-weight:bold;
}

.resumeBanner {
    margin-top:-10px;
    color: #9b7a56;
    text-shadow: 0.2px 0.5px 0.2px white;
}

.textBanner {
    font-style: italic;
    max-width: 675px;
}

.socialButtons {
    margin-top: 2em;
    display: flex;
    flex-direction: row;
}

.socialButtons a {
    text-decoration: none;
}

.socialButtons a div span {
    margin: 0 0.25em;
}

.btn-left {
    text-align: center;
    padding: 0.4em 1em;
    border-radius: 4px;
    border: 1px solid #9b7a56;
    color: white;
}

.btn-left:hover {
    text-decoration: none;
    background: #9b7a56;
}

.btn-center, .btn-right {
    text-align: center;
    padding: 0.4em 1em;
    border-radius: 4px;
    margin-left: 1em;
    border: 1px solid #9b7a56;
    color: white;
}

.btn-center:hover, .btn-right:hover{
    text-decoration: none;
    background: #9b7a56;
}

.imageBanner {
    margin-right: 50px;
    margin-left: 25px;
}

.imageBanner img {
    width: 75%;
}

@media only screen and (max-width: 800px) {
    .infoBanner {
        padding: 1em;
        text-align: center;
        margin: 0 1em;
    }
}

@media only screen and (max-width: 890px) {
    .imageBanner img {
        width: 100%;
    }
}

@media only screen and (max-width: 768px) {
    .bannerDiv {
        padding: 0 0 1em 0;
        display: block;
        text-align: center;
    }

    .resumeBanner {
        margin: 10px 0 15px 0;
        font-size: 30px;
        width: 100%;
    }

    .textBanner {
        text-align: justify;
    }

    .socialButtons {
        justify-content: center;
    }

    .imageBanner {
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 2em;
    }

    .imageBanner img {
        width: 50%;
        max-width: 640px;
    }
}
</style>