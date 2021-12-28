<template>
    
     <div>

        <h2>Esta é a descrição da pessoa: {{ nome }}</h2>

        <p>{{ email }}</p>

        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>

        <p v-else>Estou em busca de novas oportunidades.</p>

        <p>Utilizo as seguintes tecnologias para BackEnd:</p>

        <ul>

            <li v-for="tecnology, index in backend_tecnologies" v-bind:key="index"> {{ tecnology }} </li>
            
        </ul>

        <p>Utilizo as seguintes tecnologias para FrontEnd:</p>

        <ul>

            <li v-for="tecnology in frontend_tecnologies" :key="tecnology.id"> {{ tecnology.language }} </li>
            
        </ul>

        <div>

            <button @click="showEmail"> {{ textoBotao }} </button>

        </div>

        <p class='teste' v-show="mostrar_email">Mande uma mensagem para: {{ email }}</p>

        <p>Para acessar meu portifólio <a v-bind:href="meu_link" target="_blank">basta clicar aqui.</a></p>

        <Picture/>
    </div>

</template>

<script>

    import Picture from './Picture.vue'

    export default {

        name: 'Info',

        components: {

            Picture

        },

        props: {

            email: String

        },

        data() {

            return {

                esta_trabalhando: false,

                mostrar_email: false,

                meu_link: 'https://google.com',

                textoBotao: 'Mostrar e-mail',

                backend_tecnologies:  ['JAVASCRIPT', 'PHP', 'PYTHON'],

                frontend_tecnologies: [

                    {id:1, language: 'HTML'},

                    {id:2, language: 'CSS'},

                    {id:3, language: 'VUE'}

                ]

            }

        },

        methods: {

            showEmail() {

                this.mostrar_email = !this.mostrar_email

                if(!this.mostrar_email){

                    this.textoBotao = 'Mostrar e-mail'

                } else {

                    this.textoBotao = 'Esconder e-mail'

                }

            }

        }

    }

</script>
