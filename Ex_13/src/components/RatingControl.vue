<template>
    <ul>
        <li :class="{ active: activeOption === 'poor' }">
            <button @click="active('poor')">Poor</button>
        </li>
        <li :class="{ active: activeOption === 'average' }">
            <button @click="active('average')">Average</button>
        </li>
        <li :class="{ active: activeOption === 'greate' }">
            <button @click="active('greate')">Great</button>
        </li>
    </ul>
</template>

<script>
export default {
    props:["modelValue"],
    emits:["update:modelValue"],
    // data() {
    //     return {
    //         activeOption: this.modelValue,
    //     };
    // },
    // computed:{
    //     activeOption(){

    //     }
    // },  
    methods: {
        active(option) {
            this.$emit('update:modelValue', option)  
        }
    },
}
</script>
<style scoped>
.active {
    border-color: purple;
}
.active button{
    color: purple;
}

ul {
    list-style: none;
    margin: 0.5rem 0;
    padding: 0;
    display: flex;
}

li {
    margin: 0 1rem;
    border: 1px solid white;
    padding: 1rem;
    display: flex;

}
</style>