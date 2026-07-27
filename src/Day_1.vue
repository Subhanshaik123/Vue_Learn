<script setup>
const msg = "My name is Subhan"
const msg1 = "I'm a Full Stack Developer & Vue.js Developer"
const msg2 = "https://github.com/subhanshaik786"
const today = new Date().toLocaleDateString("en-GB")
</script>

<template>
  <div class="myclass">

    <center>
      <h1 id="class">{{ msg }}</h1>
      <h2 style="color: blue;">{{ msg1 }}</h2>
    </center>

    <center>
      <h2>Hyderabad</h2>
    </center>

    <center>
      <h2>Github:</h2>
      <a :href="msg2" target="_blank">{{ msg2 }}</a>
    </center>

    <center>
      <h2>Skills</h2>

      <h4>HTML5</h4>
      <h4>CSS3</h4>
      <h4>JavaScript</h4>
      <h4>ReactJS</h4>
      <h4>Bootstrap</h4>
      <h4>Vue.js</h4>
    </center>
    <footer>
      <center>
        <h3>Today's Date: {{ today }}</h3>
      </center>
    </footer>

  </div>
</template>

<style scoped>
.myclass {
  background-color: cyan;
  padding: 20px;
}

#class {
  color: blueviolet;
}

h2 {
  font-family: Arial, sans-serif;
}

h4 {
  color: red;
  margin: 10px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

footer {
  color: white;
  background-color: black;
  padding: 15px;
  margin-top: 30px;
}

a {
  text-decoration: none;
  color: darkblue;
  font-size: 18px;
}

a:hover {
  color: red;
}
</style>