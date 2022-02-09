<template>
  <div class="hello">
    <h1>{{ counter }}</h1>
    <input type="Button" value="Increment" @click="subscribe">
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },

  data: function () {
    return {
      counter: 0
    }
  },

  methods: {
    subscribe: function() {
      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ topicName: "projects/theta-ember-340812/topics/GmailTrigger", labelIds: ["INBOX"] })
        };
    fetch("https://www.googleapis.com/gmail/v1/matthijsvanspelde1999@gmail.com/me/watch", requestOptions)
      .then(response => console.log(response));
    }
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
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
