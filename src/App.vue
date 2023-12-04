<script>
    import { ref } from 'vue'
    export default {
        setup() {
            const isTrue = ref(false)
            return { isTrue }
        }
    }
</script>

<template>
    <header>
        <div>
            <h2>{{ isTrue }}</h2>
        </div>
        <div id="conditional-rendering">
            <h1>conditional rendering</h1>
            <button @click="isTrue = !isTrue"> {{ isTrue }} </button>
        </div>
        <div id="is-true">
            <p v-if="isTrue" :style="{ color: 'green' }">
            is true is currently true
            </p>
            <p v-else :style="{ color: 'red' }">
            is true is currently false
            </p>
        </div>

        <div id="class">
            <h1>Class and styles</h1> 
            <ul>
                <li :class = "{ isActive: isTrue }">normal vue class</li>
                <li :class = "[ isTrue ? 'isActive' : '', 'highPriority' ]">class bound with arrays</li>
            </ul>
        </div>
    </header>
    <RouterView />
</template>

<style>

.isActive {
    color: blue;
}

.highPriority {
    font-weight: bold;
    border: 1px solid white;
    text-align: center;
}

</style>
