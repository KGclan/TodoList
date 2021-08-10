<template>
    <div class="counter">
        <h3>Всего задач : {{ tasks_count }}</h3>
    </div>
</template>
<style lang="sass" scoped>

</style>
<script>
export default {
    name: "Counter",
    props:["tasks_count"]
}
</script>