<script setup>
import { Icon } from '@iconify/vue';
const props = defineProps({
    todo: {
        type: Object,
        required: true,
    },
});

</script>



<template>

    <li>
        <input type="checkbox" :checked="todo.isCompleted">
        <div class="todo">
            <input type=" text" :value="todo.todo">
            <span>{{ todo.todo }}</span>

        </div>

        <div class="todo-actions">
            <Icon icon="ph:check-circle-light" class="icon" width="32" height="32" style="color: #2fb92d" />
            <Icon icon="ph:pencil-fill" class="icon" width="32" height="32" style="color: #2fb92d" />
            <Icon icon="ph:trash" class="icon" width="32" height="32" style="color: #f95e5e" />

        </div>
    </li>

</template>




<style lang="scss" scoped>
.input-wrap {
    display: flex;
    transition: 250ms ease;
    border: 2px solid #41b080;

    &.input-err {
        border-color: red;
    }

    &:focus-within {
        box-shadow: 0 -4px 6px -1px rgb(0 0 0 / 0.1),
            0 -2px 4px -2px rgb(0 0 0 / 0.1);
    }

    input {
        width: 100%;
        padding: 8px 6px;
        border: none;

        &:focus {
            outline: none;
        }
    }

    button {
        padding: 8px 16px;
        border: none;
    }
}

.err-msg {
    margin-top: 6px;
    font-size: 12px;
    text-align: center;
    color: red;
}
</style>