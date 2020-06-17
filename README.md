# CSS 骨架屏闪动背景原理

```html
<div class="skeleton-wrapper">
  <ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</div>
```

```less
.skeleton-wrapper {
  margin: 10px;
  border-radius: 10px;
  border: 1px solid #ccc;
  overflow: hidden;
  padding: 10px;
}

li {
  list-style: none;
  height: 40px;
  background: linear-gradient(90deg, #f2f2f2 25%, red 35%, #f2f2f2 50%);
  background-size: 400% 100%;
  border-radius: 4px;
  animation: skeleton-loading 1.4s ease infinite;
  background-position: 100% 50%;

  & + & {
    margin-top: 10px;
  }
  &:first-child {
    width: 40px;
    border-radius: 100%;
  }
  &:nth-child(2),
  &:last-child {
    width: 50%;
  }
  &:nth-child(3) {
    width: 70%;
  }
}

@keyframes skeleton-loading {
  0% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
}
```

<iframe src="https://codepen.io/xing_he/pen/dyGOGVp?editors=1100" height="500px" height="100%" scrolling="auto"></iframe>

## 参考

- [CSS 中 background-position 使用技巧](https://www.cnblogs.com/ecmasea/p/9150595.html)
- [CSS 实现 Skeleton Screen 骨架屏效果](https://www.jb51.net/css/730828.html)
