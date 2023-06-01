<template>
  <div class="home">
    <div class="clac">
      <div class="resualt">
        <div class="header">
          <p class="para">calculator</p>
          <p class="para">Github</p>
        </div>
        <h1 class="backg">CALCULATER</h1>
      </div>
      <div class="reset" @click="reset()">C</div>
      <input type="text" class="inp-clac" v-model="number2" placeholder="0" />
      <div class="box-num-op">
        <div
          @click="saynum(number)"
          class="num"
          :value="number"
          v-for="(number, index) in numbers"
          :key="index"
        >
          {{ number }}
        </div>
        <div class="delete op" @click="dele()">delet</div>
        <div class="op" @click="equal()">=</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  data() {
    return {
      message: "here data is a property",
      number2: "",
      numbers: [1, 2, 3, "+", 4, 5, 6, "-", 7, 8, 9, "*", 0, "00", "/", "%"],
      peopledetals: [
        {
          name: "ahd",
          age: 22,
        },
      ],
    };
  },
  methods: {
    saynum(num) {
      this.number2 += num;
    },
    equal() {
      this.number2 = eval(this.number2);
    },
    reset() {
      this.number2 = "";
    },
    dele() {
      var ss = this.number2.split("").slice(0, length - 1);
      this.number2 = ss.join("");
    },
  },
};
</script>

<style>
.clac {
  padding: 12px;
  position: absolute;
  background-color: #432454;
  width: 450px;
  text-align: center;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  border-radius: 29px;
}
.cm {
  display: flex;
}
.backg {
  font-size: 60px;
  opacity: 0.2;
  font-weight: bold;
  color: #edc8c8;
  border: 1px solid;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
}
.header .icon {
  color: white;
}
.header .para {
  color: white;
  font-size: 16px;
  padding: 6px 26px;
  margin: 13px 7px;
  border: 1px solid #ffffff7a;
  border-radius: 10px;
  cursor: pointer;
  background-color: #717a8ba1;
}
.header .para:hover {
  background-color: #ffffff7a;
}
.reset {
  background-color: red;
  width: 40px;
  height: 35px;
  font-size: 32px;
  font-weight: bold;
  color: white;
  cursor: pointer;
  border-radius: 10px;
  position: ABSOLUTE;
  bottom: 381px;
  left: 18px;
}
.num,
.op {
  flex: calc(69% / 4);
  cursor: pointer;
  padding: 7px;
  font-size: 34px;
  margin: 5px 9px;
  font-weight: bold;
  color: white;
  border: 1px solid #7f7e83;
  border-radius: 10px;
  background-color: #bab9b9a1;
}
.op:hover {
  background-color: #717a8ba1;
}
.num:hover {
  background-color: #717a8ba1;
}
.box-num-op {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  background-color: #432454;
  border-radius: 10px;
}
.inp-clac {
  width: 96%;
  text-align: right;
  border: none;
  font-size: 34px;
  background-color: #eee;
  outline: none;
  border-radius: 10px;
}
.clac .resualt {
  min-height: 240px;
}
</style>
