<template>
  <!--TODO OPtions-->
  <div class="options-container">
    <ul>
      <li>growlithe</li>
      <li>swarmpet</li>
      <li>3</li>
      <li>4</li>
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style>
ul {
  list-style-type: none;
}

li {
  background-color: white;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  width: 200px;
  margin-bottom: 10px;
  cursor: pointer;
}

li:hover {
  background-color: rgba(0, 0, 0.5);
}
.options-container{
    justify-content: center;
    display: flex;
}

</style>