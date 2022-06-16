<template>
    <div>
        <p>name:</p>
        <input v-model="model.name" />
        <p>age:</p>
        <input v-model.number="model.age" />
        <button @click="handleAddFormButtonClick()">Добавить</button>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
    data() {
        return {
            model: {
                id: '',
                name: '',
                age: 0
            }
        }
    },
    methods: {
        handleAddFormButtonClick: function () {
            this.model.id = uuidv4();
            this.$emit("submit", this.model)
        }
    }
}


</script>