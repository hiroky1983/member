<template>
  <div>
    <input
      type="text"
      placeholder="名前を入力"
      class="input"
      v-model="newMember"
    />
    <button>追加</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      members: [],
      newMember: "",
    };
  },
};
</script>

<style>
.input {
  padding: 4px;
}
</style>
