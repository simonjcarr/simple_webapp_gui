<template>
  <div>
    Hello World
  </div>
  <div>The time from the API is: {{apiTime}}</div>
</template>

<script>
export default {
  data() {
    return {
      apiTime: 123,
    }
  },
  async mounted() {
    try {
      this.apiTime = await fetch("https://simple_webapp.soxprox.com/api/v1/gettime");
    } catch(e) {
      this.apiTime = "ERROR: Unable to fetch from API"
    }
  }
};
</script>
