<template>
    <center class="contactDiv">
        <form id="form" class="form" autocomplete="off">
            <h3>Lets Get In Touch!</h3>
            <label for="name">Name <span>*</span></label>
            <input name="name" type="text" id="name" placeholder="Alex Ros" required>
            <label for="email">Email <span>*</span></label>
            <input name="email" type="text" id="email" placeholder="example@domain.com" required>
            <label for="message">Message</label>
            <textarea id="message" name="message"></textarea>
            <button type="submit" class="btn btn-success">Enviar mensaje</button>
        </form>
        <a href="mailto:me@rosarlanzon5@gmail.com" id="mailto"></a>
    </center>
    <div class="contact">
        <Footer />
    </div>
</template>

<script>
import Footer from '@/components/Footer.vue'


export default {
    name: 'ContactView',
    components: {
        Footer
    }, 
    mounted() {
        const $form = document.querySelector('#form')
        const $buttonMailto = document.querySelector('#mailto')

        $form.addEventListener('submit', handleSubmit)

        function handleSubmit(event) {
            event.preventDefault()
            const form = new FormData(this)
            $buttonMailto.setAttribute('href', `mailto:rosarlanzon5@gmail.com?subject=Nombre: ${form.get('name')} - Correo: ${form.get('email')}&body=${form.get('message')}`)
            $buttonMailto.click()
        }
    }
}
</script>

<style scoped>
.contactDiv {
    margin: 25px;
    font-family: system-ui;
}

.form h3, .form label, .form button {
    display: block;
    margin: 10px;
}

.form input {
    display: block;
    margin: 5px;
    width: 500px;
    height: auto;
}

.form textarea {
    resize: none;
    display: block;
    margin: 10px;
    width: 600px;
    height: 351px;
}

.form label span {
    color: rgb(211, 76, 76);
}
</style>
