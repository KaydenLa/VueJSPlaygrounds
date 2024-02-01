<script setup>
import { reactive, ref, computed } from 'vue'

const isActive = ref(true)
const hasError = ref(true)

const refColor = ref('green')
const refFontsize = ref('3vw')

const author = ref({
    name: 'John Doe',
    books: [
        'Vue 2 - Advanced Guide',
        'Vue 3 - Basic Guide',
        'Vue 4 - The Mystery'
    ],
    count: 1
})

const awesome = ref(true)
//const avalue = ref(true)

const parentMessage = ref('Parent')
const items = ref([{ message: 'Foo' }, { message: 'Bar' }])

// a computed ref
const publishedBooksMessage = computed(() => {
    return author.value.count > 0 ? 'Yes' : 'No'
})

// function printBooksMessage() {
//   return author.value.books.length > 0 ? 'Yes' : 'No'
// }

const printBooksMessage = () => {
    return author.value.books.length > 0 ? 'Yes' : 'No'
}

const returnRed = () => {
    return 'red'
}
const returnBlue = () => {
    return 'blue'
}
</script>

<!-- <template>
  <p>Author Info: {{ author.name }}</p>
  <span>{{ publishedBooksMessage }}</span>
  <p>self defined function call</p>
  <span>{{ printBooksMessage() }}</span>
</template> -->

<template>
  <div class="static" 
       :style="{color: returnBlue(), 'font-size': refFontsize}">
    <p>Welcome to binding-example.</p>
  </div>
  
  <div class="static" 
       :class="{active: isActive, 'text-danger': hasError, myDiv: isActive}">
    <p>Welcome to binding-example.</p>
  </div>
<!-- </template> -->

<!-- <template> -->
    <button @click="awesome = !awesome">toggle</button>

    <!-- <h1 v-if="awesome">Condition met</h1> -->
    <h1 v-if="awesome">Condition met</h1>
    <h1 v-if="awesome">Vue is awesome!</h1>
    <h1 v-else>Oh no </h1>
<!-- 
    <div id="example1">
        <h1 v-show="awesome">Condition met</h1>
    </div>

    <div id="example2">
        <li v-for="item in items">
            {{ item.message }}
        </li>
    </div>

    <li v-for="(item, index) in items">
        {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li> -->
</template>

<style scoped>
.myDiv {
    border: 5px outset red;
    background-color: lightblue;
    text-align: center;
}
</style>