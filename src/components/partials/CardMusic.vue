<template>
  <div class="d-flex flex-column text-center">
      <div class="box p-3">
          <div class="image">
               <img class="img-fluid" :src="details.poster">
          </div>

          <div class="title">
           <h2 class="text-center text-light text-uppercase">{{details.title}}</h2>
       </div>
        
        <div class="author">
            <span>{{details.author}}</span>
        </div>
        
        <div class="year">
            <span>{{details.year}}</span>
        </div>
        
      </div>
    </div>
</template>

<script>
export default {
    name: 'CardMusic',
    props: ['details']
}
</script>

<style scoper lang="scss">
   .box {
       background-color: #2e3a46;
       margin: 10px 0px;
       padding: 5px;
       height: 100%;

      .title {
          h2{
              margin-top: 20px;
              font-size: 16px;
          }
      }

      .author, .year {
          color: gray;
          font-size: 13px;
          }
   }
</style>