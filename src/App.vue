<template>
  <div id="app">
    <router-view />
  </div>
</template>
<script>
export default {
  created () {
    let arr = [{ id: '1' }, { id: '2' }, { id: '3' }, { id: '0' }, { id: '4' }, { id: '5' }, { id: '1' }, { id: '2' }]
    let newArr = arr.map(v => v.id)
    let result = new Array();
    newArr.forEach((item, index) => {
      if (newArr.indexOf(item) !== newArr.lastIndexOf(item) && !result.find(v => v.id == arr[index].id)) {
        result.push(arr[index])
      }
    })
    console.warn(result);




    //   console.log(arr);
    //   let newArr = new Array();
    //   arr.forEach(item => {
    //     if (!newArr.find(i => i.name == item.name)) {
    //       newArr.push(item)
    //     }
    //   })
    //   console.log(newArr);//[{ name: '1' },{ name: '2' }]
  }}

</script>


<style>
html,body,#app{
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}
</style>
