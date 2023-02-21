<template>
  <div class="create-container">
    <div class="done-container">
      <h1
        @dblclick="deleteNotes(index)"
        v-for="(item, index) of doneNotes"
        :key="index"
        class="noteText"
        :style="noteStyle[index]"
      >
        {{ item }}
      </h1>
    </div>

    <div class="create-form" v-if="isVisible">
      <form class="form">
        <textarea
          v-model="inputValue"
          class="textarea"
          placeholder="Write note...."
          maxlength="200"
        ></textarea>
        <span @click="addNotes" class="check material-symbols-outlined"
          >add_circle</span
        >
        <span @click="deleteForm" class="cancel material-symbols-outlined"
          >cancel</span
        >
      </form>
    </div>

    <button @click="createForm" class="btn btn-create">Create Notes</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isVisible: false,
      inputValue: "",
      doneNotes: [],
      noteStyle: [],
      i: 0,
      margin: ["-5px", "1px", "5px", "10px", "15px", "20px"],
      color: ["#33FF57", "#FF5733", "#FFBD33", "#DBFF33", "#75FF33", "#33FFBD"],
      rotate: [
        "rotate(3deg)",
        "rotate(1deg)",
        "rotate(-1deg)",
        "rotate(-3deg)",
        "rotate(-5deg)",
        "rotate(-10deg)",
      ],
    };
  },

  methods: {
    createForm() {
      this.isVisible = true;
    },

    deleteForm() {
      this.isVisible = false;
    },

    addNotes() {
      const newNote = this.inputValue;
      this.doneNotes.push(newNote);
      this.noteStyle.push(this.getNoteStyles());
      this.inputValue = "";
    },

    deleteNotes(index) {
      this.doneNotes.splice(index, 1);
      this.noteStyle.splice(index, 1);
    },

    getNoteStyles() {
      const margin = this.randomMargin();
      const backgroundColor = this.randomColor();
      const transform = this.randomRotate();
      return { margin, backgroundColor, transform };
    },

    randomMargin() {
      return this.margin[Math.floor(Math.random() * this.margin.length)];
    },

    randomColor() {
      if (this.i > this.color.length - 1) {
        this.i = 0;
      }
      return this.color[this.i++];
    },

    randomRotate() {
      return this.rotate[Math.floor(Math.random() * this.rotate.length)];
    },
  },
};
</script>

<style>
.create-container {
  width: 95%;
  margin: auto;
}

.done-container {
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  margin-top: 20px;
  margin-left: 5%;
}

.btn {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  font-size: 26px;
}

.form {
  position: absolute;
  top: 26%;
  left: 40%;
}

.textarea {
  font-family: "Lacquer", cursive;
  font-size: 1.5rem;
  box-shadow: 10px 10px 20px 10px rgba(193, 28, 28, 0.79);
  outline: none;
  border: none;
  width: 270px;
  height: 270px;
  padding: 40px 25px 25px 25px;
  border-radius: 10px;
}

.btn-create {
  font-family: "Big Shoulders Inline Text", cursive;
  color: rgb(239, 132, 132);
}

.material-symbols-outlined {
  color: rgb(32, 112, 108);
  width: 16px;
  height: 16px;
}

.check {
  position: absolute;
  right: 17%;
  top: 4%;
}

.check:hover {
  color: rgb(106, 229, 106);
}

.cancel {
  position: absolute;
  right: 5%;
  top: 4%;
}

.cancel:hover {
  color: red;
}

.noteText {
  font-family: "Lacquer", cursive;
  font-size: 1.5rem;
  width: 250px;
  height: 250px;
  font-size: 26px;
  padding: 25px;
  margin-top: 10px;
  overflow: hidden;
  box-shadow: 0px 10px 24px 0px rgba(0, 0, 0, 0.75);
}
</style>