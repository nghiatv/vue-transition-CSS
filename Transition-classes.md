### Transition classes

Sẽ có 6 class cho phép chúng ta thêm các hiệu ứng vào 6 giai đoạn \(thực ra sẽ là 4 thời điểm và 2 giai đoạn \) khi mà enter/leave transition:

1. `v-enter `: trạng thái bắt đầu. Nó được thêm vào trước khi elements được thêm vào và xóa frame ngay khi quá trình thêm vào hoàn tất.
2. `v-enter-active:` khởi động trạng thái. Nó được thêm vào trước khi elements được insert \( cùng thời điểm với v-enter \), và được xóa khi hiệu ứng transition hoàn tất. Class này thường được sử dụng để định nghĩa các duration, delay .. của transition.
3. `v-enter-to`: Chỉ có ở phiên bản 2.1.8 trở lên. Kết thúc quá trình thêm vào. Sẽ được thêm vào sau khi elements được insert \( cùng thời điểm với thằng `v-enter` bị remove đi \), và được xóa đi khi transition/animation hoàn tất.
4. `v-leave`: tương tự như `v-enter` nhưng thay vào đó là đi ra \(leaving\) chứ không còn là đi vào nữa.
5. `v-leave-active`: giống với `v-enter-active` nhưng áp dụng cho trạng thái đi ra\( leaving\) của elements.
6. `v-leave-to`: tương tự như `v-enter-to` nhưng thay vào đó là trạng thái ra chứ không phải là vào.

Nếu từ ngữ khiến bạn khó hiểu thì mô tả bằng hình ảnh dưới đây sẽ khiến bạn dễ hiểu hơn:

![](https://vuejs.org/images/transition.png)



Mỗi class sẽ được thêm 1 prefix ở phía trước là `v-` khi bạn sử dụng `transition` mà không khai báo name. Nếu bạn có khai báo tên cho transiton ví dụ như `<transition name="aura" >` thì thay vì `v-enter` mà sẽ là `aura-enter.`



