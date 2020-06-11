<template>
  <div>
    <div class="alert" :class="mode" role="alert">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Alert",
  props: ["mode"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.primary {
  color: #fff;
  background-color: #032141;
  border-color: #032141;
}

.success {
  color: #fff;
  background-color: #034b03;
  border-color: #034b03;
}

.danger {
  color: #fff;
  background-color: #e4270f;
  border-color: #e4270f;
}

.alert {
  position: relative;
  padding: 0.75rem 1.25rem;
  margin-bottom: 1rem;
  border: 1px solid transparent;
  border-radius: 0.25rem;
}
</style>
