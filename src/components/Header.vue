<template>
    <header>
        <h1>{{ title }}</h1>
        <Button v-show="homePage" @button-clicked="$emit('toggle-add-task')"
            :text="showingAddTask ? 'Close' : 'Add Task'" :color="showingAddTask ? 'red' : 'green'" />
    </header>
</template>

<script>
import Button from "./Button.vue"
export default {
    name: "Header",
    props: {
        title: String,
        showingAddTask: Boolean
    },
    components: { Button },
    computed: {
        homePage() {
            return (this.$route.path === "/")
        }
    }
}
</script>

<style>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>