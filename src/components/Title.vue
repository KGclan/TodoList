<template>
    <div class="title">
        <h1 class="title__h1">{{ title }}</h1>
    </div>    
</template>
<style lang="sass" scoped>
    .title
        .title__h1      
</style>
<script>
export default {
    name: "Title",
    props:["title"],
}
</script>