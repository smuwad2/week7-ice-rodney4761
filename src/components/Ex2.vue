<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'],
                itemAdded: ''
            }
            
        },
        methods: {
            addItem() {
                this.items.push(this.itemAdded)
            },
            deleteItem(index) {
                this.items.splice(index, 1);
            }

        }
    }

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul id="shoppingCart">
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
        <button @click="deleteItem(index)">Delete!</button>
      </li>
    </ul>
    <input type="text" v-model="itemAdded" />
    <button @click="addItem">Add!</button>

   
</template>