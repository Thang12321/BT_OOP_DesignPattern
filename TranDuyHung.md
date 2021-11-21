+ Trong folder Factory:
- file CoinFactory.java chứa lớp CoinFactory thực chất là một lớp Factory hỗ trợ việc việc khởi tạo các các đối tượng thuộc các lớp Coin khác nhau nhằm che giấu việc phương thức khởi tạo và thống nhất việc khởi tạo các đối tượng cụ thể thuộc các lớp như CopperCoin, GoldCoin đều implements 1 interface là Coin
//     public class CoinFactory{
//	public static Coin getCoin(CoinType type)
//
//	}
- mặc dù tác giả của project gán static cho method getCoin nhưng không bắt buộc; tác dụng không phải khởi tạo factory trong khi vẫn có thể sử dụng tính năng trả về đối tượng nhằm khởi tạo chúng được
//	dưới đây là một ví dụ khác về factory:
//	public abstract class Shape{
//		String color;
//	}
//	public class Square extends Shape {
//		public Square(){}
//	}
//	public shapeFactory{
//		public Shape getShape(String shapeType) {
//			if(shapeType.equals("SQUARE")
//				return new Square();

+ Trong folder AbstractFactory:
- Trước khi xem xét project của tác giả thì ta phải lí giải được thế nào Abstract Factory. Abstract Factory là Factory của Factory nghĩa là 1 cái Factory tổng cho phép trả về các Factory con nhằm che giấu việc khởi tạo các factory con. Bổ sung ví dụ vào bài factory của tác giả nếu ta có Coin Factory cho phép sinh ra các loại coin thì ta có thể có thêm CashFactory sinh ra các loại cash tiền mặt khi đó ta có thể tạo một moneyFactory sinh ra cả 2 loại factory đó.
- Trong project trên git thì abstractFactory là FactoryMaker và các Factory là ElfKingdomFactory và  OrcKingdomFactory -> đây chính là 2 Factor giống như CoinFactory ở ví dụ trên.
//	public static KingdomFactory makeFactory(KingdomType type)
// -> đây là phương thức cho phép sinh ra các Factory.
+ Trong folder Bridge:
- Tóm tắt về mẫu thiết kế Bridge trước khi đi vào phân tích project: đây là mẫu thiết kế cho phép tách phần thực thi và phần trừu tượng để chúng khác nhau độc lập; làm cho các lớp cụ thể độc lập với các lớp thực thi interface.
- Ví dụ: có nhiều chiếc máy tính và nhiều chip cpu nếu tạo ra từng bản sao cụ thể của từng máy tính khác nhau gắn với từng cpu khác nhau rất tốn thời gian thay vào đó có thể tạo ra một đối tượng duy nhất thay đổi hiệu năng với các loại cpu gắn vào.
- mẫu bridge trên Git: nếu bạn chơi game rồi thì sẽ biết trong game có các loại bùa(enchantment: FlyingEnchantment & SoulEatingEnchantment) với các hiệu quả khác nhau cùng với vô số loại vũ khí(weapon) cụ thể là class Hammer và class Sword giả sử có hàng trăm các loại bùa khác nhau thì việc tạo hằng trăm method của từng weapon gắn với các loại bùa là không khôn ngoan.
- tóm tắt mẫu bridge của project:
	public interface Weapon {
  		void wield();
  		void swing();
  		void unwield();
  		Enchantment getEnchantment();
	}
	public class Sword implements Weapon {
  		private final Enchantment enchantment;
  			
		public Sword(Enchantment enchantment) {
    			this.enchantment = enchantment;
  		}
		...........
		@Override
  		public Enchantment getEnchantment() {
    			return enchantment;
  		}
	}
-> sự thay đổi của bùa chú (enchantment) từ phương thức khởi tạo sẽ dẫn đến thay đổi trong method getgetEnchantment mà không phải tạo ra các method với từng loại bùa nếu thay đổi method thành trả về tác dụng của bùa thì sẽ thay đổi với từng loại bùa mà không phải tạo ra vô số các method tương ứng với từng loại bùa xong lại phải xét để thực hiện phương thức ứng với loại bùa đã cho.
