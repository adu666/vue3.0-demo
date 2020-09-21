<template>
<div class="hello">
    <h1>{{ msg }}</h1>
    <h1>count:{{count}}</h1>
    <div>count * 2 = {{doubleCount}}</div>
    <button @click="add">点击</button>
</div>
</template>

<script>
import {
    ref,
    computed,
    watch
} from "vue";
export default {
    name: "HelloWorld",
    props: {
        msg: String,
    },
    setup() {
        const count = ref(0);

        const add = () => {
            console.log(count);
            count.value++;
        };
        watch(() => count.value, (val) => {
            console.log(`count is ${val}`);
        });
        const doubleCount = computed(() => count.value * 2);
        return {
            count,
            add,
            doubleCount
        };
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
h3 {
    margin: 40px 0 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
</style>
