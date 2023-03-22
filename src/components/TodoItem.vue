<template>
    <li>
        <input type="checkbox" :checked="isChecked">
        <div>{{ title }}</div>
    </li>
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
    li {
        display: flex;
        justify-content: space-between;
    }
</style>

