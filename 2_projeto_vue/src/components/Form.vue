<template>

   <div>

        <h2>Meu Formulário: </h2>

        <form action="" @submit="enviarFormulario($event)">

            <InputText/>

            <br>
            
            <InputText/>

            <br>

            <input type="text" v-model="email">

            <br>
            
            <Submit/>

        </form>

   </div>

</template>

<script>

    import InputText from './form/InputText.vue'

    import Submit from './form/Submit.vue'

    export default {

        name: 'Form',

        components: {

            InputText,

            Submit

        },

        data() {

            return {

                email:""

            }

        },

        methods: {

            enviarFormulario(e) {

                e.preventDefault();

                const email = this.email

                console.log("O email é: " + email);

                console.log("Formulário Enviado!");

            }

        }

    }

</script>
