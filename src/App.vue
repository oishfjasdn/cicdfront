<template>
  <div id="app">
    <h1>前端项目</h1>
    <button @click="sendData">发送数据</button>
    <div v-if="response">
      <h2>API 反馈结果:</h2>
      <pre>{{ response }}</pre>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      response: null
    }
  },
  methods: {
    async sendData() {
      try {
        const response = await fetch('http://1p.wztj.net:8080/cicd.wztj.net/api/test', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({ message: 'Hello from frontend' })
        });
        const data = await response.json();
        this.response = JSON.stringify(data, null, 2);
      } catch (error) {
        this.response = 'Error: ' + error.message;
      }
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  font-size: 2em;
  margin-bottom: 40px;
}

button {
  background-color: #4CAF50;
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin: 4px 2px;
  cursor: pointer;
  border-radius: 4px;
}

button:hover {
  background-color: #45a049;
}

pre {
  background-color: #f0f0f0;
  padding: 20px;
  border-radius: 4px;
  text-align: left;
  max-width: 600px;
  margin: 20px auto;
  white-space: pre-wrap;
}
</style>