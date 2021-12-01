<template>
    <div>
        <input v-model='changedName' placeholder='Change KevVar'>
        <button @click='changeName'>OK</button>
    </div>
</template>

<script>
export default {
    name: 'Component2',
    props:{
        userName: String
    },
    data() {
        return {
            changedName:'',
        }
    },
    methods: {
        changeName(){
            this.$emit('changeName', this.changedName)
        }
    },
}
</script>