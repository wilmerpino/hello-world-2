<template>
    <h1>{{ texto}}</h1>
</template>

<script>
export default {
    name: 'Titulo',
    props: {
        texto: String
    }
}
</script>
/*
scoped = Ambito local del componente
*/
<style scoped>
h1 {
    color: peru;
}
</style>