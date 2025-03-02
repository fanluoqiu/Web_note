# CSS+HTML


## 边框头像

<style>
    .user-avatar {
      border-radius: 50%;
      height: 200px;
      width: 200px;
      border: 2px solid #ddd;
      padding: 10px;
    }
    .avatar-image {
      border-radius: 50%;
      height: 100%;
      width: 100%;
      object-fit: cover; /*按图片原有尺寸比例来裁剪*/

      
    }
  </style>
  <body>    
    <center>    
    <div class="user-avatar">
      <img class="avatar-image" src="Images/ex1.jpg" />
    </div>
    </center>
  </body>

```html

<style>
    .user-avatar {
      border-radius: 50%;
      height: 200px;
      width: 200px;
      border: 2px solid #ddd;
      padding: 10px;
    }
    .avatar-image {
      border-radius: 50%;
      height: 100%;
      width: 100%;
      object-fit: cover; /*按图片原有尺寸比例来裁剪*/
    }
  </style>
  <body>
    <div class="user-avatar">
      <img class="avatar-image" src="Images/ex1.jpg" />
    </div>
  </body>
```



<style>
  body,
  html {
    height: 100%;
  }
  .container {
    border: 1px solid #ddd;
    height: 100%;
    /*核心代码*/
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .container .img {
    width: 100px;
    height: 100px;
    background-color: #ddd;
    border-radius: 100%;
    overflow: hidden; /*超出部分显示隐藏*/
  }
</style>
<body>
  <div class="container">
    <div class="img">...</div>
    <div class="title">....</div>
    <div class="info">....</div>
  </div>
</body>