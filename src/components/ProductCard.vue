<template>
  <div class="card">
    <h2>{{title}}</h2> 
    <p> цена - {{price}}</p>
    <img :src="imageUrl" alt="Обложка товара">
    <div class="card_footer">
      <button>Купить</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props:{
    title:{
      type: String,
      default:''
    },
    price:{
      type: Number,
      default: 0
    },
    imageUrl:{
      type: String,
      default:''
    }
  }
}
</script>

<style scoped>
  .card{
    max-width: 350px;
    border: 1px solid black;
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    overflow: hidden;
  }
  .card_footer {
    background-color: black;
  }
  .card_footer button {
    background: red;
    border-radius: 10px;
    padding: 10px 40px;
    cursor: pointer;
    border: none;
    color:white;
    font-weight: bold;
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .card_footer button:hover {
    background: rgb(167, 70, 70);
    color:wheat;    
  }
</style>