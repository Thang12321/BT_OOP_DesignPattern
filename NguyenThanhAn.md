Decorator pattern:
* Trong folder Decorator, có các folder là pizza, starbuzz, có các file java như là ToppingDecorator.java, CondimentDecorator.java là các các lớp decorator(hay wrapper).
```
public abstract class ToppingDecorator extends Pizza {
	Pizza pizza;
	public abstract String getDescription();
}
```
* Như trong folder Pizza, người dùng muốn order 1 chiếc pizza nhưng sau đó muốn thêm nhiều loại topping khác vào chính chiếc pizza đó, cũng như việc số tiền tổng chi cho chiếc pizza đó phải tăng theo số topping dc thêm vào, file ToppingDecorator.java hay là decorator pattern giúp chúng ta thực hiện việc này, thêm chức năng mới vào đối tượng pizza hiện tại mà ko làm ảnh hưởng đến nó.
  => Kiểu thiết kế này có cấu trúc hoạt động như một lớp bao bọc (wrap) cho lớp hiện có. Mỗi khi cần thêm tính năng mới, đối tượng hiện có được wrap trong một đối tượng mới (decorator class).
```
public class Cheese extends ToppingDecorator {
	
 
	public Cheese(Pizza pizza) {
		this.pizza = pizza;
	}
 
	public String getDescription() {
		return pizza.getDescription() + ", Cheese";
	}
 
	public double cost() {
		return pizza.cost(); // cheese is free
	}
}
```
Composite pattern:
* Trong folder composite có file Menu.java dùng để lưu trữ tập hợp các menu components hay các đối tượng tương tự nhau, để xử lí các đối tượng này hoạt động như 1 đối tượng duy nhất (theo cùng 1 cách). Menu.java cài đặt các phương thức được định nghĩa trong interface menuComponent bằng cách ủy nhiệm cho các thành phần con xử lý
  => Composite patterns.
```
import java.util.Iterator;
import java.util.ArrayList;

public class Menu extends MenuComponent {
	ArrayList<MenuComponent> menuComponents = new ArrayList<MenuComponent>();
	String name;
	String description;
  
	public Menu(String name, String description) {
		this.name = name;
		this.description = description;
	}
 
	public void add(MenuComponent menuComponent) {
		menuComponents.add(menuComponent);
	}
 
	public void remove(MenuComponent menuComponent) {
		menuComponents.remove(menuComponent);
	}
 
	public MenuComponent getChild(int i) {
		return (MenuComponent)menuComponents.get(i);
	}
 
	public String getName() {
		return name;
	}
 
	public String getDescription() {
		return description;
	}
 
	public void print() {
		System.out.print("\n" + getName());
		System.out.println(", " + getDescription());
		System.out.println("---------------------");
  
		Iterator<MenuComponent> iterator = menuComponents.iterator();
		while (iterator.hasNext()) {
			MenuComponent menuComponent = 
				(MenuComponent)iterator.next();
			menuComponent.print();
		}
	}
}
```

Strategy patterns:
* Folder challenge trong Strategy có file ShareStrategy.java chứa các hành vi có thể có của 1 strategy, mà ở trong folder này là share các photo đã chụp dc bằng các hành vi như post lên social media, texting photo va email photo.
```
@FunctionalInterface
public interface ShareStrategy {
	public void share();
}
```
* Đây là 1 strategy pattern, đóng gói từng thuật toán, method lại, và dễ dàng thay đổi linh hoạt nó bên trong object, ý nghĩa của việc chia ra các hành vi có thể có của 1 đối tượng như vậy là để tạo ra một tập hợp các thuật toán để xử lý chức năng đó và lựa chọn thuật toán nào mà chúng ta thấy đúng đắn nhất khi thực thi chương trình. Ví dụ như trong trường hợp này, ta có thể chọn các hành vi share khác nhau của 1 object là photo :
```
public class Txt implements ShareStrategy {
	public void share() {
		System.out.println("I'm txting the photo");
	}
}

public class Social implements ShareStrategy {
	public void share() {
		System.out.println("I'm posting the photo on social media");
	}
}

public class Email implements ShareStrategy {
	public void share() {
		System.out.println("I'm emailing the photo");
	}
}
```

Iterator:
* Trong folder iterator/dinermerger có file Iterator.java, đây là 1 lớp iterator, lớp này có tác dụng để truy cập tuần tự tới các phần tử của một đối tượng.
```
public interface Iterator {
	boolean hasNext();
	MenuItem next();
}
```
* Lớp trên cung cấp một interface duy nhất để duyệt qua các phần tử của một tập hợp. Như trong trường hợp này thì lớp iterator dc dùng để duyệt qua các items của 1 menu.
```
import java.util.ArrayList;

public class ArrayListIterator implements Iterator {
	ArrayList<MenuItem> items;
	int position = 0;
 
	public ArrayListIterator(ArrayList<MenuItem> items) {
		this.items = items;
	}
 
	public MenuItem next() {
		MenuItem item = items.get(position);
		position = position + 1;
		return item;
	}
 
	public boolean hasNext() {
		if (position >= items.size()) {
			return false;
		} else {
			return true;
		}
	}
}
```

