<template>
    <div class="mb-2" :id="'task-' + index">
        <input type="checkbox" :checked="isChecked" v-model="isChecked">
        <div style="margin-left: 1rem;" :class="[isChecked ? 'task-done' : '']">{{ title }}</div>
        <div class="action-btn" style="margin-left: 1rem;">
            <button class="btn btn-sm" @click="$emit('edit', [index])" >Edit</button>
            &nbsp;
            <button @click="$emit('remove', [index])" class="btn btn-sm">Delete</button>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            isChecked: false,
        }
    },
    props: {
        title: String,
        index: Number
    },
}
</script>
<style scoped>
div {
    display: flex;
    justify-content: flex-start;
}

.task-done {
    text-decoration: line-through;
}
</style>

