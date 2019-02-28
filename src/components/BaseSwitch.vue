<template>
  <div class="switch-container">
    <input id="switch" type="checkbox" class="switch" checked />
    <label for="switch"></label>
  </div>
</template>

<script>
export default {};
</script>
<style lang="less" scoped>
@switchHeight: 30px;
@switchWidth: 60px; /*改变大小只需要改变这个两个的值，后面会用到这两个值*/
.switch-container {
  height: @switchHeight;
  width: @switchWidth;
  margin-bottom: 5px;

  .switch {
    display: none;
    &:checked ~ label:after {
      opacity: 1;
    }

    &:checked ~ label:before {
      opacity: 0;
    }

    &:checked ~ label {
      background-color: red;
    }
  }

  label {
    display: block;
    background-color: #eeeeee;
    height: 100%;
    width: 100%;
    cursor: pointer;
    border-radius: 25px;
    &:before {
      content: '';
      display: block;
      border-radius: 25px;
      height: 100%;
      width: @switchHeight;
      background-color: white;
      opacity: 1;
      box-shadow: 1px 1px 1px 1px rgba(0, 0, 0, 0.08);
      -ms-transition: all 0.2s ease; /* IE 9 */
      -moz-transition: all 0.2s ease; /* Firefox */
      -webkit-transition: all 0.2s ease; /* Safari and Chrome */
      -o-transition: all 0.2s ease; /* Opera */
    }
    &:after {
      position: relative;
      top: -@switchHeight;
      left: @switchHeight;
      content: '';
      display: block;
      border-radius: 25px;
      height: 100%;
      width: @switchHeight;
      background-color: white;
      opacity: 0;
      box-shadow: 1px 1px 1px 1px rgba(0, 0, 0, 0.08);
      -ms-transition: all 0.2s ease; /* IE 9 */
      -moz-transition: all 0.2s ease; /* Firefox */
      -webkit-transition: all 0.2s ease; /* Safari and Chrome */
      -o-transition: all 0.2s ease; /* Opera */
    }
  }
}
</style>


