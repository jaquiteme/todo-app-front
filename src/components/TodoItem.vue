<template>
    <div>
        <input type="checkbox" :checked="isChecked" v-model="isChecked">
        <div :class="[isChecked ? 'task-done':'']">{{ title }}</div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            isChecked: false
        }
    },
    props: {
        title: String
    }
}
</script>
<style scoped>
    div {
        display: flex;
        justify-content: space-between;
    }

    .task-done {
        text-decoration: line-through;
    }
</style>

