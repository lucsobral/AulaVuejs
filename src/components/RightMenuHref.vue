<template>
  <a :href="link">{{ description }}</a>
</template>

<script>
export default {
    props:{
        link: String,
        description: String
    }
}
</script>

<style>

</style>