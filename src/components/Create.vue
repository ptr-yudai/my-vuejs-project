<template>
<div>
  <h2>Create New TODO</h2>
  <div>
    <label for>
      期限：
      <input type="text" v-model="newTodoDate">
    </label>
    <br>
    <label for>
      タイトル：
      <input type="text" v-model="newTodoTitle">
    </label>
    <br>
    <label for>
      内容：
      <input type="text" v-model="newTodoContents">
    </label>
    <br>
    <button @click="addTodo">追加</button>
  </div>
</div>
</template>

<script>
export default {
    name: "Create",
    props: {
	todo: {
	    type: Array,
	    default: []
	}
    },
    data() {
	return {
	    id: 0,
	    newTodoTitle: "",
	    newTodoContents: "",
	    newTodoDate: ""
	}
    },
    methods: {
	addTodo() {
	    this.todo.push(
		{
		    title: this.newTodoTitle,
		    contents: this.newTodoContents,
		    date: this.newTodoDate,
		    state: 0,
		    id: this.id
		}
	    );
	    this.id += 1;
	}
    }
};
</script>
