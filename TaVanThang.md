- Trong folder Buider:
+ Trong HouseBuilder.java khởi tạo lớp abstract HouseBuilder có chứa các phương thức abstract sử dụng mẫu thiết kế Fluent Interface Pattern trả về chính HouseBuider

  public abstract HouseBuilder addWalls();
  
  public abstract HouseBuilder addRoof();
  
  public abstract HouseBuilder addWindows();
  
+ Các lớp WoodHouseBuilder, StoneHouseBuilder, GingerbreadHouseBuilder kế thừa các thuộc tính trong lớp abstract HouseBuilder
=> Tách tiến trình xây dựng 1 đối tượng phức tạp sao cho một tiến trình tạo được các biểu diễn khác nhau => Builder Design Pattern

- Trong folder Adapter:
+ Trong DuckAdapter.java có 2 hàm quack() và fly(), các lớp Turkey và Drone implements lớp Duck và thay đổi 2 hàm quack() và fly() cho phù hợp
  //  Ví dụ:
  //    public void quack() {
  //		  drone.beep();
  //	  }
  //	  public void fly() {
  //		  drone.spin_rotors();
  //		  drone.take_off();
  //	  }
=> Sử dụng mẫu thiết kế Adapter.

- Trong folder Prototype:
+ File Monster.java khởi tạo lớp Monster, lớp này được dùng làm đối tượng mẫu để quy định các loại đối tượng của lớp Dragon, Drakon. 2 lớp này kế thừa lớp Monster và tạo mới nhờ sao chép đối tượng mẫu
//	Ví dụ:
//	public Monster copy() throws CloneNotSupportedException {
//		return (Monster)this.clone();
//	}
=> Sử dụng mẫu thiết kế Prototype

- Trong folder Singleton:
+ Các folder trong Singleton đều chứa ví dụ về mẫu thiết kế Singleton, các file Singleton.java đều chứa 1 phương thức instance và chỉ duy nhất 1 điểm truy xuất toàn cục đến nó
//	Ví dụ:
//	public static Singleton getInstance() {
//		if (uniqueInstance == null) {
//			uniqueInstance = new Singleton();
//		}
//	return uniqueInstance;
//	}
=> Mẫu thiết kế Singleton được sử dụng với tần suất cao do việc tạo instance cho mỗi đối tượng là cần thiết

- Trong folder Flyweight:
+ Lớp interface Tree chia sẻ thông tin cho 2 lớp con của nó là ConiferTree và DeciduousTree giúp giảm dung lượng bộ nhớ thông qua chia sẻ các đối tượng
Ví dụ: Phương thức isWithinRange và display ở trong Tree.java được chia sẻ cho 2 lớp con:
Trong Tree:
//	public default boolean isWithinRange(LocalDate aDate) {
//		Month month = aDate.getMonth();
//		return (month.getValue() > 2) && (month.getValue() < 11);
//	}
Trong ConiferTree:
//	public void display(int x, int y) {
//		System.out.println("Conifer tree is located at " + x + ", " + y);
//	}
Trong DeciduousTree:
//	public void display(int x, int y) {
//		System.out.println("Deciduous tree is located at " + x + ", " + y);
//		if (!this.isWithinRange(LocalDate.now())) {
//			System.out.println("The tree currently has no leaves");
//		}
//	}
