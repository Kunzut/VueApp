<template>
  <div>
    <h2>Home Page</h2>
    
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. A accusantium adipisci enim excepturi explicabo maiores provident quam reprehenderit totam vero.</p>

    <router-link to="/todos" class="linkTo">Go to Todos</router-link>
  </div>
</template>

<style>
  .linkTo {
    color: #000;
    text-decoration: none;
    font-size: 16px;
    font-weight: bold;
    outline: none;
  }

  .linkTo:hover {
    color: #4dafe5;
    text-decoration: underline;
    cursor: pointer;
  }
</style>