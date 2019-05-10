<template>
<div>
  <h1>My TODO List</h1>
  <hr>
  <list :todo.sync="todo" />
  <hr>
  <create :todo.sync="todo" />
  <hr>
</div>
</template>

<script>
import Create from "./Create.vue";
import List from "./List.vue";

export default {
    name: "Todo",
    components: {
	List,
	Create,
    },
    data() {
	return {
	    todo: []
	}
    }
};
</script>

<style></style>
