<template>
  <div id="app">
    <main>
      <div class="search-box">
        <input type="text" class="search-bar" placeholder="search..." />
      </div>
    </main>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      api_key:'5cf91bfff72d64c70fa6ccb0cf0ee978'
    }
  }
}
</script>

<style>
* {
  margin:0 ;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-family: 'montserrat' , sans-serif;
}

#app{
  background-image: url('./assets/cold-bg.jpg');
}
</style>
