<template>
  <div>
    <h3>Profile Page</h3>
    <h3>This is {{ user_id }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user_id: this.$route.params.user_id
    };
  },

  methods: {
    updateId() {
      this.user_id = this.$route.params.user_id;
    }
  },
  watch: {
    $route: "updateId"
  }
};
</script>

<style scoped></style>
