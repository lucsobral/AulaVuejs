<template>
  <div class="card border-0">
    <div class="card-body">
      <p>
        <i class="far fa-clock"></i>
        <small class="ml-2">{{ date }}</small>
      </p>
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">
        {{ resume }}
      </p>
      <button class="btn btn-primary">Leia mais...</button>
    </div>
  </div>
</template>

<script>
export default {
    props:{
        date: String,
        title: String,
        resume: String
    }
};
</script>

<style>
</style>