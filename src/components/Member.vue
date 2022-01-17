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
    <div class="memberWapper">
      <ul>
        <li v-for="member in members" v-bind:key="member">
          {{ member }}
        </li>
      </ul>
    </div>
    <div id="resultFIeld">
      {{ result }}
    </div>
    <button class="btn">追加</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      members: [],
      newMember: "",
      result: "",
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
.memberWapper {
  height: 300px;
}
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
#resultFIeld {
  background-color: white;
  width: 60%;
  height: 70px;
  margin: 0 auto;
  border-radius: 40px;
}
</style>
