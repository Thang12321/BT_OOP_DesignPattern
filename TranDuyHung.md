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
+ 