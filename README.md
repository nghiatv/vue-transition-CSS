# [Tổng quan](README.md)

* [Transition Classes](chapter1.md)
* [CSS Transition](css-transition.md)
* [CSS Animation](css-animation.md)



# Transtion trong Vue js

Vue cung cấp cho chúng ta nhiều cách để thêm hiệu ứng transition cho các DOM khi chúng ta tiến hành thêm, sửa hay xóa chúng. Cụ thể sẽ bao gồm:

* tự động thêm vào các class để phục vụ việc CSS transition và animations
* hợp nhất với thư viện CSS của bên thứ 3, như là Animate.css
* sử dụng Javascript để tương tác vào các Dom thông qua các transition hook
* hợp nhất với thư viên JS của bên thứ 3 như là Velocity.js

## Transition trong Elements/Components

Vue cung cấp cho chúng ta 1 `transtion`   component cho phép chúng ta thêm các hiệu ứng vào/ra \(entering/leaving - sau đoạn này mình sẽ để tiếng anh để sát vơi tên của các class CSS\) cho tất cả các element hay component thỏa mãn điều kiện sau:

* Render có điều kiện \(sử dụng `v-if )`
* Hiển thị có điều kiện \(sử dụng `v-show` \)
* Components động
* Components không phải là root nodes

Một cách đơn gian để hiểu vỉ dụ trên như sau:

```HTML
<div id="demo">
  <button v-on:click="show = !show">
    Toggle
  </button>
  <transition name="fade">
    <p v-if="show">hello</p>
  </transition>
</div>
```

```js
new Vue({
  el: '#demo',
  data: {
    show: true
  }
})
```

```css
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s
}
.fade-enter, .fade-leave-to {
  opacity: 0
}
```

Để hiểu rõ hơn thì chúng ta cần xem xem điều gì xảy ra bên trong `transition` component khi mà ta thêm hay xóa đi 1 elements trong nó:

1. Vue sẽ tự động thêm vào các hiệu ứng CSS thông qua các class
2. Nếu transiton component mà có chứa các Javascript hooks, thì các hooks này sẽ được gọi vào thời điểm phù hợp.
3. Nếu mà không có các hiệu ứng CSS hay các JS hooks thì nó được thực hiện ngay lập tức và chẳng có hiệu ứng nào ở đây cả.

### 



