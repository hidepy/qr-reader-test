<script setup lang="ts">
import { ref, reactive } from "vue";
import jsQR from 'jsqr';

interface User {
  firstName: string;
  lastName: string;
  age: number;
}

const count = ref<number>(0); // ジェネリクスで型注釈

const user: User = reactive({} as User);

// TODO: https://qiita.com/U_sagi/items/12cc39487a863e0136a0 , https://zenn.dev/sdkfz181tiger/articles/096dfb74d485db , https://qiita.com/kan_dai/items/4331aae12f5f2d3ad18d を使って実装する


const setUser = ():void=> {
  user.firstName = 'John'
  user.lastName = 'Doe'
  user.age = 25
}
</script>

<template>
  <h1>RefComponent</h1>
  {{ count }}
  <button @click="count++">クリック</button>

  <div>FullName: {{ `${user.firstName} ${user.lastName}` }}</div>

  <button @click="setUser">set user</button>

</template>