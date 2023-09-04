<template>
    <section  class="form" :class="{ 'hidden': isComponentHidden }">
        <form action="">
            <label>
                IMIĘ<span>*</span>
                <input v-model="name" placeholder="- wpisz -" type="text" name="name" required>
            </label>
            <label>
                NAZWISKO<span>*</span>
                <input v-model="surname" placeholder="- wpisz -" type="text" name="surname" required>
            </label>
            <label>
                ADRES E-MAIL<span>*</span>
                <input v-model="email" placeholder="- wpisz -" type="email" name="email" required>
            </label>
            <p><span>*</span> - pola wymagane</p>
            <label>
                <input v-model="accept" type="checkbox" required>
                <span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</span>
            </label>
            <button @click.prevent="formSubmit({name, surname, email, accept})" type="submit">Wyślij</button>
            <p v-if="showErrorMessage">Proszę uzupełnić wymagane pola</p>

            <img @click="" src="./../assets/svg/close.svg" alt="">
        </form>
    </section>
</template>

<script>
export default {
    methods: {
        formSubmit(formObject) {
            if (this.name && this.email && this.email && this.accept) {
                console.log(formObject);
            } else {
                this.showErrorMessage = true;
            }
        },
        
    },
    data() {
        return {
            name: '',
            surname: '',
            email: '',
            accept: false,
            isComponentHidden: false,
            showErrorMessage: false,
        }
    }
}
</script>

<style lang="scss">
.form {
    position: relative;
    background-color: white;
    box-shadow: 0px 0px 30px #FF4359;
    border-radius: 40px;
    position: fixed;
    top: 25%;
    left: 40%;
    padding: 30px;
    input {
        display: block;
        padding: 10px;
        margin-block: 10px;
        border-radius: 7px;
        border-color: #AFAFAF;
    }
    span {
        color: #FF4359;
    }
    button {
        text-align: center;
        background-color: #FF4359;
    }
    p {
        color: #FF4359;
    }
    img {
        position: absolute;
        right: 15px;
        top: 15px;
        cursor: pointer;
    }
}
.hidden {
    visibility: hidden;
}
</style>

this.name && this.email && email && accept
