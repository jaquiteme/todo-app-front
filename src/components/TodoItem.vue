<template>
    <div @mouseover="displayBtn" @mouseleave="removeBtn" :id="'task-' + index">
        <input type="checkbox" :checked="isChecked" v-model="isChecked">
        <div style="margin-left: 1rem;" :class="[isChecked ? 'task-done' : '']">{{ title }}</div>
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
    methods: {
        displayBtn() {
            let currTask;
            let div = document.createElement("div");
            div.setAttribute("id", "actions")
            div.append("Some text");
            currTask = document.getElementById('task-' + this.index)
            currTask.append(div)
        },
        removeBtn: function () {
            let div = document.getElementById('actions');
            div.remove();
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

