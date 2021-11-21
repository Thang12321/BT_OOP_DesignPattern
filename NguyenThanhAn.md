Decorator pattern:
* Trong folder Decorator, có các folder là pizza, starbuzz, có các file java như là ToppingDecorator.java, CondimentDecorator.java là các các lớp decorator(hay wrapper) .
* Như trong folder Pizza, người dùng muốn order 1 chiếc pizza nhưng sau đó muốn thêm nhiều loại topping khác vào chính chiếc pizza đó, cũng như việc số tiền tổng chi cho chiếc pizza đó phải tăng theo số topping dc thêm vào, file ToppingDecorator.java hay là decorator pattern giúp chúng ta thực hiện việc này, thêm chức năng mới vào đối tượng pizza hiện tại mà ko làm ảnh hưởng đến nó.
=> Kiểu thiết kế này có cấu trúc hoạt động như một lớp bao bọc (wrap) cho lớp hiện có. Mỗi khi cần thêm tính năng mới, đối tượng hiện có được wrap trong một đối tượng mới (decorator class). 

Composite pattern:
* Trong folder composite có file CompositeIterator.java dùng để lưu trữ tập hợp các menu components hay các đối tượng tương tự nhau, để xử lí các đối tượng này hoạt động như 1 đối tượng duy nhất (theo cùng 1 cách). CompositeIterator cài đặt các phương thức được định nghĩa trong interface menuComponent bằng cách ủy nhiệm cho các thành phần con xử lý
=> Composite patterns.