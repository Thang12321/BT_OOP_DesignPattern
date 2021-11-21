- Trong folder Buider:
+ Trong HouseBuilder.java khởi tạo lớp abstract HouseBuilder có chứa các phương thức abstract sử dụng mẫu thiết kế Fluent Interface Pattern trả về chính HouseBuider
  //public abstract HouseBuilder addWalls();
	//public abstract HouseBuilder addRoof();
	//public abstract HouseBuilder addWindows();
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
