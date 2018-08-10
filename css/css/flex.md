---
description: base 基础实例
---

# flex

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<style>
  .box{
    border: #3a8ee6 1px solid;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content:flex-start;
    align-items: flex-start;
    width: 209px;
    /*height: auto;*/
    height: 104px;
    margin: 0 auto;
  }
  .item{
    text-align: center;
    width: 50px;
    height: 50px;
    border: 1px solid #dd6161;
    flex: 0 0 24%;
  }
  .item:nth-child(odd){
    height: 40px;
  }
  .item:nth-child(even){
    height: 60px;
  }
  .item:nth-child(4)~.item{
    position: relative;
    top: -20px;
    align-self:flex-end;
  }
  .item:nth-child(4)~.item:nth-child(odd){
    height: 60px;
  }
  .item:nth-child(4)~.item:nth-child(even){

    background: blue;height: 40px;
  }

  /*.odd .item:nth-child(odd){*/
    /*height: 40px;*/
  /*}*/
  /*.even .item:nth-child(odd){*/
    /*height: 60px;*/
  /*}*/

</style>
<body>
<div class="box odd">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
  <div class="item">6</div>
  <div class="item">7</div>
  <div class="item">8</div>
</div>
<!--<div class="box even">-->
  <!--<div class="item">5</div>-->
  <!--<div class="item">6</div>-->
  <!--<div class="item">7</div>-->
  <!--<div class="item">8</div>-->
<!--</div>-->
</body>
</html>

```

