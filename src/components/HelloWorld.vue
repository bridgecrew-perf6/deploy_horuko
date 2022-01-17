<template>
  <div class="hello">
   <button @click="teste()" >GET CERTIFICATOR</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    teste() {
      fetch("https://val.portalunico.siscomex.gov.br/portal/api/autenticar", {
        method: "POST",
        headers: {
          "role-type": "IMPEXP",
          "content-type": "application/json",
        },
      })
        .then(response => {
          console.log(response);
        }).catch(e =>{
          console.log(e)
        });
    },
  },
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
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
