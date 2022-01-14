<template>
  <div>
    <div>
      <input
        type="text"
        placeholder="名前を入力"
        class="input"
        v-model="newMember"
      />
      <button class="btn" @click="clickAdd">追加</button>
    </div>
    <div>
      <ul>
        <li v-for="member in members" v-bind:key="member">
          {{ member }}
        </li>
      </ul>
    </div>
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
  methods: {
    clickAdd() {
      if (this.newMember === "") {
        return;
      }
      this.members.push(this.newMember);
      this.newMember = "";
    },
  },
};
</script>

<style>
.input {
  padding: 6px;
  background-color: white;
  border-radius: 14px;
}
.btn {
  margin-left: 4px;
  background-color: black;
  color: white;
  padding: 6px;
  border-radius: 14px;
}
.btn:hover {
  background-color: gray;
  cursor: pointer;
}
</style>
