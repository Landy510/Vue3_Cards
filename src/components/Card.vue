<script setup>
  import { defineProps, ref } from 'vue'
  import fireUrl from '../assets/images/fire.png'
  const props = defineProps({
    id: Number,
    type: String,
    duration: String,
    burned: String
  })

  const isActive = ref(false)

  function handleMouseEnter(toggle) {
    isActive.value = toggle
  }

</script>


<template>
  <template v-if="type">
    <div 
      :class="[
        'card', 
        isActive ? 'active' : ''
      ].join(' ')"
      @mouseenter="handleMouseEnter(true)"
      @mouseleave="handleMouseEnter(false)"
    >
      <div class="mask">
        Learn More
      </div>
      <h3 class="header">
        {{props.type}}
      </h3>
      <div class="main">
        <div class="item">
          <span class="itemLabel">Duration</span>
          <span class="itemTxt">{{props.duration}}</span>
        </div>
        <div class="item">
          <span class="itemLabel">Calorie Burned</span>
          <span class="itemTxt">
              <img 
                :src="fireUrl" 
                alt=""
                width="20"
                height="20"
              >
              {{props.burned}}
          </span>
        </div>
      </div>
    </div>
  </template>
  <template v-else>
    <div class="card noResult">
      <h2 class="header">Ramble CrossFit</h2>
      <p class="slogan">Why not hit the gym</p>
      <p class="slogan">Start your Journey</p>

      <a 
        type="button"
        class="btn"
      >Register</a>
    </div>
  </template>
</template>

<style scoped>
  .card + .card {
    margin-left: 50px;
  }

  .card .mask {
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    top: -100%;
    background-color: rgba(0, 0, 0, 0.4);
    border-radius: 25px;
    transition: 0.5s;

    display: flex;
    justify-content: center;
    align-items: center;

    color: #fff;
    font-size: 24px;
    font-weight: 600;
  }

  .card.active .mask {
    top: 0
  }

  .card {
    position: relative;
    width: 230px;
    height: 210px;
    border-radius: 25px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
    padding: 20px;
    color: #aec4ff;
    overflow: hidden;
  }

  .card:hover {
    cursor: pointer;
  }

  .card .header {
    border-left: 4px solid #aec4ff;
    padding-left: 10px;
    margin-bottom: 15px;
    font-weight: 600;
  }

  .card .item {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
    
  }

  .card .item .itemLabel {
    color: #979797;
  }

  .card .item .itemTxt {
    display: flex;
    align-items: center;
    color: #000;
    font-weight: 600;
  }

  .card .item .itemTxt img{
    display: inline-block;
    margin-right: 5px;
    vertical-align: middle;
  }

  .noResult {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .noResult .header {
    padding-left: 0;
    font-weight: 600;
    border: none;
    white-space: nowrap;
  }

  .noResult .slogan {
    color: #000;
    font-weight: 600;
  }

  .noResult .btn {
    color: #aec4ff;
    padding: 10px 20px;
    border: 1px solid #aec4ff;
    border-radius: 25px;
    margin-top: auto;
  }
</style>