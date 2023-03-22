<template>
    <div>
        <input type="checkbox" :checked="isChecked">
        <div>{{ title }}</div>
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
</style>

