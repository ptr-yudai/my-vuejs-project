<template>
<div>
  <h2>TODO List</h2>
  <ul>
    <li v-for="item in todo" :key="item.id">
      <item :item="item" :todo.sync="todo" />
    </li>
  </ul>
</div>
</template>

<script>
import Item from "./Item.vue";

export default {
    name: "List",
    data() {
	return {
	    checked: []
	}
    },
    components: {
	Item
    },
    props: {
	todo: {
	    type: Array,
	    default: []
	}
    }
};
</script>

<style>
a {
    margin: 4px;
}
</style>
