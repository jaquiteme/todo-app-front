<template>
    <div @mouseover="hiddenBtn(true)" @mouseleave="hiddenBtn(false)" class="mb-2" :id="'task-' + index">
        <div>
            <input type="checkbox" :checked="isChecked" v-model="isChecked">
            <div style="margin-left: 1rem;" :class="[isChecked ? 'task-done' : '']">{{ title }}</div>
        </div>
        <div v-if="displayActionBtn" class="action-btn"
            style="margin-left: 1rem; position: absolute; z-index: 10; right: 0;">
            <button class="btn btn-primary btn-sm" @click="$emit('edit', [index])">Edit</button>
            &nbsp;
            <button @click="$emit('remove', [index])" class="btn btn-danger btn-sm">Delete</button>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            isChecked: false,
            displayActionBtn: false
        }
    },
    props: {
        title: String,
        index: Number
    },
    methods: {
        hiddenBtn: function (state) {
            this.displayActionBtn = state
        }
    }
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

