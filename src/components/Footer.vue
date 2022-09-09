<template>
    <footer class="bg-dark text-center text-lg-start tk-acuta">
        <div class="container p-4">
            <div class="row">
                <div class="col-lg-6 col-md-12 mb-4 mb-md-0">
                    <h5 class="text-uppercase">Alex Ros</h5>
                    <p class="p-footer">
                        Thanks for stopping by! <br>
                        <a href="/" class="footer-links">Portfolio</a> |
                        <a href="/getintouch" class="footer-links">Get In Touch</a>
                    </p>
                </div>
                <div class="col-lg-6 col-md-12 mb-4 mb-md-0">
                    <h5 class="text-uppercase">Social Networks</h5>
                    <div>
                        <a href="https://www.instagram.com/aleesrox/" target="_blank" rel="noopener noreferrer" class="fa fa-instagram"></a>
                        <a href="https://twitter.com/alesrox" target="_blank" rel="noopener noreferrer" class="fa fa-twitter"></a>
                        <a href="https://github.com/alesrox" target="_blank" rel="noopener noreferrer" class="fa fa-github"></a>
                    </div>
                </div>
            </div>
        </div>
        <div class="subfooter p-3">
            © 2022 Copyright:
            <a class="subfooter-link white-text" href="">Alex Ros</a>
        </div>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
.justify-text {
    text-align: justify;
    text-justify: auto;
}

footer.bg-dark {
    color: #fff;
}

.subfooter {
    background-color: rgba(0, 0, 0, 0.2);
}

.footer-links {
    margin: 0 15px;
    color: #42b983;
}

.white-text {
    color: rgb(200, 200, 200);
}

.white-text:hover {
    color: rgb(200, 200, 200);
}

.fa {
    font-size: 40px;
    margin: 5px;
    color: var(--icon-color);
}

.fa:hover {
    font-size: 45px;
    margin: 0 2.65px;
    color: var(--icon-color);
}

.p-footer span {
    color: #2a9a36;
}
</style>