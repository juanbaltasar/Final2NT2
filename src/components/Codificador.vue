<template>
  <div>
    <textarea name="" v-model="textoACodificar" placeholder="Inserte el texto a codificar!"></textarea>
    <h1>{{TextoCodificadoAMayuscula}}</h1>
  </div>
</template>

<script>

  export default  {
    name: 'Codificador',
    props: [],
    mounted () {

    },
    data () {
      return {
        textoACodificar: ''
      }
    },
    methods: {

    },
    computed: {
      TextoCodificadoAMayuscula(){
        const TextoEnArray = this.textoACodificar.toLowerCase().split('')
            let TextoCodificado = ''
            for (const letra of TextoEnArray) {
                if (letra === 'a') {
                    TextoCodificado += 'u'
                }
                else if (letra === 'e') {
                    TextoCodificado += 'o'
                }
                else if (letra === 'o') {
                    TextoCodificado += 'e'
                }
                else if (letra === 'u') {
                    TextoCodificado += 'a'
                }
                else{
                    TextoCodificado += letra
                }
            }
            return TextoCodificado.toUpperCase()
    }
    }
}


</script>

<style scoped lang="css">
</style>
