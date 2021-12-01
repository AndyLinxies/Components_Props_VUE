<template>
    <div>
        <p>How are you <span> {{userName}}</span>?</p>
    </div>
</template>

<script>
export default {
    name: 'Component1',
    props:{
        userName: String
    }
}
</script>