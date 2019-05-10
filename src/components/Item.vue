<template>
<div>
  <s v-if="isDone" style="font-size: 20px;">[{{ item.date }}] {{ item.title }}: {{ item.contents }}</s>
  <span v-else style="font-size: 20px;">[{{ item.date }}] {{ item.title }}: {{ item.contents }}</span>
  <a href="#" @click="checkTodo(item.id)">済</a>
  <a href="#" @click="removeTodo(item.id)">削除</a>
</div>
</template>

<script>
export default {
    name: "Item",
    props: {
	todo: {
	    type: Array,
	    default: []
	},
	item: {
	    type: Object,
	    default: {}
	}
    },
    methods: {
	checkTodo(id) {
	    this.todo.forEach(item => {
		if (item.id === id) {
		    item.state = 1;
		}
	    })
	},
	removeTodo(id) {
	    var i;
	    for(i = 0; i < this.todo.length; i++) {
		if (this.todo[i].id === id) {
		    this.todo.splice(i, 1);
		}
	    }
	}
    },
    computed: {
	isDone() {
	    return this.item.state == 1;
	}
    }
}
</script>
