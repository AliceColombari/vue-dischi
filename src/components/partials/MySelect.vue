<template>
  <div class="selectGenre">
      <select name="" id="" @change="$emit('changeGenre', selectGenre)" v-model="selectGenre">
          <option value="">Seleziona un genere</option>
          <option value>All</option>
          <option value="rock">Rock</option>
          <option value="pop">Pop</option>
          <option value="jazz">Jazz</option>
          <option value="metal">Metal</option>
      </select>
  </div>
</template>

<script>
export default {
    name: "MySelect",
    data() {
        return {
            selectGenre: "",
        }
    }

}
</script>
    
<style scoped lang="scss">
    .selectGenre{
        padding: 50px 0px 0px 0px;
        text-align: right;
        
        select {
            width: 200px;
            padding: 5px;
            font-size: 12px;
        }
    }
</style>