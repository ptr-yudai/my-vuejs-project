<template>
<div>
  <s v-if="item.state==1" style="font-size: 20px;">[{{ item.date }}] {{ item.title }}: {{ item.contents }}</s>
  <span v-else style="font-size: 20px;">[{{ item.date }}] {{ item.title }}: {{ item.contents }}</span>
  <a href="#" @click="checkTodo(item.id)">済</a>
  <a href="#" @click="removeTodo(item.id)">削除</a>
</div>
</template>
