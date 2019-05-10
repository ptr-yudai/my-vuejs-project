<template>
<div>
  <h2>TODO List</h2>
  <ul>
    <li v-for="item in todo" :key="item.title">
      <s v-if="item.state==1" style="font-size: 20px;">[{{ item.date }}] {{ item.title }}: {{ item.contents }}</s>
      <span v-else style="font-size: 20px;">[{{ item.date }}] {{ item.title }}: {{ item.contents }}</span>
      <a href="#" @click="checkTodo(item.id)">済</a>
      <a href="#" @click="removeTodo(item.id)">削除</a>
    </li>
  </ul>
</div>
</template>

<script>
export default {
    name: "List",
    data() {
	checked: []
    },
    methods: {
	checkTodo(id) {
	    todo.forEach(item => {
		if (item.id === id) {
		    item.state = 1;
		}
	    })
	},
	removeTodo() {
	    for(i = 0; i < todo.length; i++) {
		if (todo[i].id === id) {
		    todo.splice(i, 1);
		}
	    }
	}
    },
    props: {
	todo: {
	    type: Object,
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
