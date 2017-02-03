### CSS transition

Đơn giản cực bạn chỉ cần định nghĩa các hiệu ứng CSS trong style bằng đúng tên các transition class ở phía trên mình vừa nói

Ví dụ nhé:

```HTML
 <transition name="dunno">
      <div class="vuong1 blue" v-if="show" ></div>
 </transition>
```

```css
.dunno-enter-active {
  transition: all 2s ease
}
.dunno-leave-active {
  transition: all 3s cubic-bezier(2.0, 1.5, 0.3, 1.6);
}
.dunno-enter, .dunno-leave-active{
  transform: translateY(20px);
}
```

Vậy là mình đã có được hiệu ứng theo yêu cầu. Rất đơn giản.



