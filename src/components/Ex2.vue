<script>
    export default { 
        // Add code in appropriate places
        data() {
            return {
                added: "",
                items: ['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter']
            }
        },
        methods: {
            del(item) {
                const i = this.items.indexOf(item);
                this.items.splice(i, 1)
            },

            add() {
                if (this.added != ""){
                    this.items.push(this.added);
                    this.added="";
                }
            }
        }
    }
</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
     <div v-for="item in items" :key="item">
        {{ item }} <button @click="del(item)" style="background-color: red;">Delete</button>
     </div>

    <!-- <ul id="shoppingCart">
      <li v-for="(item, index) in items" :key="index">
        {{ item }}
        <button @click="deleteItem(index)">Delete!</button>
      </li>
    </ul> -->

     <input v-model="added" style="background-color: white; color: black;" type="text">&nbsp;
     <button @click="add()" style="background-color: blue">Add!</button>
   
</template>