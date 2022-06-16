<template>
   <div>
      <table>
         <tr>
            <th>Имя</th>
            <th>Возраст</th>
         </tr>

         <ContactListRowComponent v-for="item in contactsList" :key="item.id" :item="item"/>
      </table>
      <ContactAddFormConponent @submit="handleAddFormSubmit"/>
   </div>

</template>

<script>
import ContactAddFormConponent from './ContactAddFormConponent.vue';
import ContactListRowComponent from './ContactListRowComponent.vue';

export default {
    data() {
        return {
            contactsList: [
                {
                    id: "9b1deb4d-3b7d-4bad-4bdd-2b0d7b3dcb6d",
                    name: "Петя",
                    age: 15,
                },
                {
                    id: "9b1deb4d-3b7d-4bad-5bdd-3b0d7b3dcb6d",
                    name: "Вася",
                    age: 31,
                },
                {
                    id: "9b1deb4d-3b7d-4bad-6bdd-5b0d7b3dcb6d",
                    name: "Люся",
                    age: 23,
                },
                {
                    id: "9b1deb4d-3b7d-4bad-7bdd-8b0d7b3dcb6d",
                    name: "Маша",
                    age: 55,
                },
                {
                    id: "9b1deb4d-3b7d-4bad-8bdd-4b0d7b3dcb6d",
                    name: "Гоша",
                    age: 9,
                },
            ],
        };
    },
    methods: {
        handleDeleteButtonClick: function () {
            this.contactsList.splice(this.contactsList.indexOf(this.contactsList.find((elem) => elem.id === this.id)), 1);
            this.$emit('iten', this.item)
        },
        handleAddFormSubmit(model){
         this.contactsList.push(model)
        }
    },
      
    components: { ContactAddFormConponent, ContactListRowComponent }
}
</script>