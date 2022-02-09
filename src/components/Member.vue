<template>
  <div class="wrapper">
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
      <p class="resultText">
        {{ result }}
      </p>
    </div>
    <button class="btn" @click="clickChoose">追加</button>
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
    clickChoose() {
      const resultI =
        this.members[Math.floor(Math.random() * this.members.length)];
      this.result = resultI;
      alert(`メンバーは${resultI}さんです`);
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
  width: 300px;
  margin-top: 16px;
  caret-color: #4338ca;
}
.btn {
  margin: 12px;
  background-color: black;
  color: white;
  padding: 6px;
  border-radius: 12px;
}
.btn:hover {
  background-color: gray;
  cursor: pointer;
  transition-delay: 75ms;
}
#resultFIeld {
  box-sizing: border-box;
  background-color: white;
  width: 60%;
  height: 80px;
  margin: 0 auto;
  border-radius: 40px;
  position: relative;
}
.resultText {
  box-sizing: border-box;
  position: absolute;
  left: 45%;
  top: 10%;
  font-size: 40px;
  font-weight: bold;
}
li {
  padding: 2px;
  font-size: 24px;
  display: grid;
  gap: 4px;
}
</style>
