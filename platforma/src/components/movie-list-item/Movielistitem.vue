<template>
  <div>
    <li class="list-group-item d-flex justify-content-between" v-bind:class="[{like: movie.like}, {favourite: movie.favourite }]">
        <!-- Kino nomi -->
      <span class="list-group-item-label">{{movie.name}}</span>
      <!-- Ko'rilganlar soni -->
      <input type="number" class="list-group-item-input" v-bind:value="movie.viewers" />
      <!-- Tugmalar -->
      <div class="d-flex justify-content-center align-items-center">
        <!-- Like tugmasi -->
        <button type="button" class="btn-heart btn-sm">
          <i class="fas fa-heart"></i>
        </button>
        <!-- O'chirish tugmasi -->
        <button type="button" class="btn-trash btn-sm">
          <i class="fas fa-trash"></i>
        </button>
        <!-- Yulduzcha tugmasi -->
        <i class="fas fa-star"></i>
      </div>
    </li>
  </div>
</template>
<script>
export default {
  // Movielist kelayotgan massiv uchun
  props:{
    movie: {
      type: Object,
      required: true,
    }
  },
  methods: {
    onLike() {
      
    }
  },
};
</script>
<style scoped>
.list-group-item {
    padding: 15px 20px;
    border-bottom: 1px solid #000;
}
/* .list-group-item:last-child{
    border-bottom: none;
} */
/* Kino nomi */
.list-group-item span{
    line-height: 35px;
    font-size: 20px;
    cursor: pointer;
    width: 550px;
}
/* Ko'rilganlar soni */
.list-group-item input{
    line-height: 35px;
    font-size: 20px;
    text-align: center;
    border: 0;
    outline: none;
}
/* Tugmalar */
.list-group-item button{
    width: 35px;
    height: 35px;
    margin: 3px;
    font-size: 17px;
    border: none;
    cursor: pointer;
}
/* Yurak */
.list-group-item .fa-heart{
    color: gold;
}
/* O'chirish */
.list-group-item .fa-trash{
    color: red;
}
/* Yulduz */
.list-group-item .fa-star{
    width: 35px;
    height: 35px;
    text-align: center;
    line-height: 35px;
    font-size: 16px;
    color: blue;
    transition: all 0.3s;
    transform: translateX(30px);
    opacity: 0;
}
/* Tugmalar funksionalligi */
.list-group-item.like .fa-star{
    opacity: 1;
    transform: translateX(0);
}
.list-group-item.favourite .list-group-item-label,
.list-group-item.favourite .list-group-item-input{
    color: gold;
}
</style>
