<template>
  <span class="badge" :class="typeOfLabel">
    {{ typeOfLabel }}
  </span>
</template>
<script>
import { computed } from "vue";
export default {
  props: ["type"],
  setup(props) {
    const typeOfLabel = computed(function () {
      return props.type.toLowerCase();
    });
    return { typeOfLabel };
  },
};
</script>
<style scoped>
.badge {
  white-space: nowrap;
  background-color: #ccc;
  color: #252525;
  border-radius: 30px;
  padding: 0.2rem 1rem 0.6rem;
  display: inline-block;
  margin-right: 0.6rem;
  font-size: 1.5rem;
  margin-bottom: 0.3rem;
}

.vegetarian {
  background-color: #00aa00;
  color: white;
}

.alcohol-free {
  background-color: #71008d;
  color: white;
}

.pescatarian {
  background-color: #3528f3;
  color: white;
}
.egg-free {
  background-color: #e48900;
  color: white;
}

/* 720*/
@media (max-width: 45em) {
  .badge {
    font-size: 1.3rem;
    padding: 0.1rem 1rem 0.5rem;
  }
}
</style>
