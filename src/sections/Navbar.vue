<template>
    <section class="navbar">
        <div class="nav-left">
            <div class="logo">
                <img src="./../assets/svg/LOGO_Placeholder.svg" alt="Logo">
            </div>
            <div class="nav">
                <div>
                    <a @click="scrollToSection('heroImage')">START</a>
                    <a @click="scrollToSection('about')">O MNIE</a>
                    <a @click="scrollToSection('gallery')">GALERIA</a>
                    <a @click="showForm">Kontakt</a>
                </div>
            </div>
        </div>
        <div class="social">
            <a href="https://www.facebook.com/">
                <img src="./../assets/svg/facebook.svg" alt="Facebook">
            </a>
            <a href="https://www.instagram.com/">
                <img src="./../assets/svg/instagram.svg" alt="Instagram">
            </a>
            <a href="https://www.youtube.com/">
                <img src="./../assets/svg/youtube.svg" alt="Youtube">
            </a>
        </div>
        <Form :isVisible="isFormVisible" @hide-form="hideForm"/>
    </section>
</template>

<script>
import Form from '@/components/Form.vue';

export default {
    data() {
        return {
            isFormVisible: false,
        }
    },
    components: {
        Form,
    },
    methods: {
        scrollToSection(sectionId) {
            const targetElement = document.getElementById(sectionId);
            if(targetElement) {
                targetElement.scrollIntoView({behavior: 'smooth'})
            }
        },showForm() {
            this.isFormVisible = true;
        },
        hideForm() {
            this.isFormVisible = false;
        },

    }
}
</script>

<style lang="scss">
.navbar {
    position: fixed;
    top: 0px;
    background-color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 8vh;
    width: 100%;
    border-bottom: 2px solid #FF4359;
    .nav-left {
        display: flex;
        align-items: center;
        img {
            padding-left: 20px;
        }
    }
    .nav {
        a {
            padding: 10px 30px;
            margin-inline: 15px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 0.8em;
        :hover {
            box-shadow: 5px 5px 10px #FF4359(255, 0, 0);
 
        }
        }
    }
    .social {
    margin-right: 30px;
        a {
            padding-inline: 2px;
        }
    }
}
</style>