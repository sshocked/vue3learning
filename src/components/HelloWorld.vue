<template>
  <div v-if="isShowMyDiv">Test</div>
  <button @click="switchIsShow">Click</button>

  <div>
    <ul>
      <li v-for="car in cars">{{ car }}</li>
    </ul>
  </div>


  <div>
    <h1>Новости</h1>
    <div v-for="newsItem in newsList">
      <h2>{{newsItem.title}}</h2>
      <p>{{newsItem.description}}</p>
      <a href="{{newsItem.url}}">Click</a>
    </div>
  </div>

  <div>
    <input v-model="inputTextTitle" type="text">
    <input v-model="inputTextDescription" type="text">
    <input v-model="inputTextUrl" type="text">
  </div>
  <button @click="createNewItem">Create new news</button>

</template>

<script>
export default {
  data() {
    return {
      message: "hello world",
      isShowMyDiv: false,
      cars: ["bmw", "lexus", "ferrari"],
      newsList: [
          {title: "Заголовок 1", description: "бла бла бла бла", url: "http://google.com"},
          {title: "Заголовок 2", description: "бла2 бл2а бла бла", url: "http://google.com"},
          {title: "Заголовок 3", description: "бла3 бла 3бла бла", url: "http://google.com"},
      ],
      inputTextTitle: "",
      inputTextDescription: "",
      inputTextUrl: "",
    }
  },
  methods: {
    switchIsShow () {
      this.isShowMyDiv = !this.isShowMyDiv;
    },
    createNewItem () {
      this.newsList.push({
        title: this.inputTextTitle,
        description: this.inputTextDescription,
        url: this.inputTextUrl,
      });
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
a {
  color: #42b983;
}
</style>
