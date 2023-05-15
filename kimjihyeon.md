5/1 1일차

// 이클립스를 통하여 자바 프로젝트를 생성하는 과정을 배움  
// "HelloWorld!!"를 출력해보았음

public class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("HelloWorld!!");
    }
} 

// JAVA의 동작원리를 배움

// 앞에서 배운 것과 같은 문자열을 출력하는 것 말고도 자바로 할 수 있는 일이 무엇이 있을지 알아봄

// 데스크톱 애플리케이션 만들기
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(800, 300)); // 화면에 띄워지는 창 사이즈를 조절할 수 있음
                JLabel label = new JLabel("Hello World!!", SwingConstants.RIGHT); // (RIGHT) 글자를 오른쪽에 배치함
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}

// 자바는 사물을 제어하는 데에도 사용이 가능함
// 라즈베리파이를 통해 자바로 전구를 끄고 키는 동작을 제어하는 코드를 보았음

// 자바로 안드로이드 앱을 개발하는 과정을 보았음
// 안드로이드 스튜디오를 통해 어떤 방식으로 코드가 적용되는지 살펴봄


5/2 2일차

public class Datatype{
	public static void main(String[] args) {
		System.out.println(6); // Number
		System.out.println("six"); // String
		
		System.out.println("6"); // String 6
		
		System.out.println(6+6); // 12
		System.out.println("6"+"6"); // 66
		
		System.out.println(6*6); // 36
//		System.out.println("6"*"6"); 에러나옴 문자열 간에는 * 연산자를 사용할 수 없음
		
		System.out.println("1111".length()); // 4 (length 연산은 문자열의 길이를 반환함)
//		System.out.println(111.length()); 숫자는 길이를 알려주는 연산 없음
	}
}


// 새로운 파일 쉽게 만드는 방법 New - Class 들어가서 Name에 이름 써주면 돼 (public static void main...체크하면 똑같은 코드를 만들 수 있음)


public class Number {

	public static void main(String[] args) {
		
		System.out.println(6 + 2); // 8
		System.out.println(6 - 2); // 4
		System.out.println(6 * 2); // 12 
		System.out.println(6 / 2); // 3
		
		System.out.println(Math.PI); // 3.141592653589793 - Math는 수학과 관련된 것들을 모아놓은 일종의 캐비닛과 같은 클래스
		System.out.println(Math.floor(Math.PI)); // 내림
		System.out.println(Math.ceil(Math.PI)); // 올림
	}

}

public class StringApp {

	public static void main(String[] args) {
		System.out.println("Hello World"); // String 문자열
//		System.out.println('Hello World'); 오류나옴 (의미가 달라지기 때문)
		System.out.println('H'); // Character 문자
		System.out.println("H");
		
//		System.out.println("Hello 
//				World");
		System.out.println("Hello "
				+ "World"); // 줄바꿈이 되지 않음 
		// new line 
		System.out.println("Hello \nWorld");
//		System.out.println("Hello "World""); 에러나옴 
		
		// escape
		System.out.println("Hello \"World\""); // Hello "World"
	}

}

public class StringOperation {

	public static void main(String[] args) {
		System.out.println("Hello World".length()); // 문자열의 길이를 산출
		System.out.println("Hello, [[[name]]] ... bye".replace("[[[name]]]", "duru")); // 문자열의 특정 문자열을 다른 문자열로 교체하는 명령을 내릴 수 있음
	}

}


5/3 3일차

public class Variable {

	public static void main(String[] args) {
		
		int a = 1; // Number -> integer(정수) ... -2, -1, 0, 1, 2 ...
		System.out.println(a);
		
//		int b = 1.1; 1.1은 정수가 아니기 때문에 오류남
	    double b = 1.1; // real number-> double(실수) ... -2.0, -1.0, 0, 1.0, 2.0 ...
	    System.out.println(b);
	    
	    String c = "Hello World";
	    System.out.println(c);
		
	    // 데이터 타입을 지정하는 이유 - 변수의 데이터 타입을 바로바로 판단할 수 있기 때문이
	}

}

public class Letter {

	public static void main(String[] args) {
		String name = "leezche";
		System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");
//		변수를 지정하면, 효율적으로 처리할 수 있음 
		
		double VAT = 10.0;
		System.out.println(VAT);
//		가독성과 재사용을 위해 변수를 이용하는 것은 중요한 수단 중 하나

	}

}

public class Casting {

	public static void main(String[] args) {
		double a = 1.1;
		double b = 1; // 손실이 없기 때문에 가능 
	    double b2 = (double) 1;
		System.out.println(b);
		
//		int c = 1.1; 에러남 
		double d = 1.1; // double 형으로 바꿔줌 
		int e = (int) 1.1; // 강제로 int 형으로 바꿔줌(손실이 일어남)
		System.out.println(e);
		
		// 1 to String 
		String f = Integer.toString(1); // 1을 문자열로 만들어줌(검색) 
		System.out.println(f.getClass());  // 변수가 갖고 있는 값이 어떤 타입인지 알려

	}

}

// 프로그램 - 시간의 순서에 따라서 어떤 일이 일어나는 것 
// 프로그램을 만드는 이유는 자동화를 하기 위해서 이다

public class Program {

	public static void main(String[] args) {
		
		System.out.println(1);
		System.out.println(2);
		System.out.println(3);
		
	}

}

// 위의 작업이 3줄이 아니라 1억줄에 이르는 작업을 수행한다면?
// 혼자가 아니라 수많은 사람들이 엄청나게 많이 사용하는 작업이라면?
// 굉장히 오래 걸리는 작업이라서 하염없이 붙잡고 있어야 하는 작업이라면?

// 프로그래밍의 효과 - 순차적으로 실행이되는 것을 통해서 사람이 잘 못하는 일을 기계에게 위임해서 자동화할 수 있다

// 다른 사람이 만든 자바 파일을 가져오는 방법은 복사해서 붙이면 돼

import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHome {

	public static void main(String[] args) {
		
		String id = "JAVA APT 507";
		
		// Elevator call
		Elevator myElevator = new Elevator("JAVA APT 507");
		myElevator.callForUp(1);
		
		// Security off
		Security mySecurity = new Security("JAVA APT 507");
		mySecurity.off();
		
		// Light on
		Lighting hallLamp = new Lighting(id+" / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting(id+" / floorLamp");
		floorLamp.on();

	}

}

// 이클립스에서 디버거 이용하기

// 브레이크 포인트 - 브레이크 포인트까지 코드가 실행되고 그 이후로 실행이 일시정지 되게 해줌, 다시 클릭하면 지울 수 있음
// Step over - 다음 줄에 브레이크 포인트 생성, 그 지점까지만 코드가 실행됨
// Terminate - Debug 중단 
// Step into - 코드의 자세한 실행 과정을 들여다볼 수 있음
// Step over - 한 줄을 실행 함수가 있어도 실행 후 다음으로 넘어감
// Step out - 함수를 끝까지 실행시키고 호출시킨 곳으로 되돌아 감
// Step return - 원래의 코드로 돌아가고자 할 경우에 클릭하여 돌아감
// resume - 다음 브레이크포인트를 만날 때까지 실행
// 우측의 Variable 탭에서 변수들을 확인 가능


5/4 4일차

import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHomeInput {

	public static void main(String[] args) {
		
		String id = JOptionPane.showInputDialog("Enter a ID"); // 입력값을 받을 수 있음 
		String bright = JOptionPane.showInputDialog("Enter a Bright level");
		
		// Elevator call 
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		
		// Security off 
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		// Light on
		Lighting hallLamp = new Lighting(id+" / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting(id+" / floorLamp");
		floorLamp.on();
		
	    DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
	    moodLamp.setBright(Double.parseDouble(bright)); // 문자열을 double로 데이터 타입을 변환함 
	    moodLamp.on();

	}

}

import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHomeInput {

	// parameter, 매개변수 
	public static void main(String[] args) {
		
		String id = args[0];
		String bright = args[1];
		
		// Elevator call 
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		
		// Security off 
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		// Light on
		Lighting hallLamp = new Lighting(id+" / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting(id+" / floorLamp");
		floorLamp.on();
		
	    DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
	    moodLamp.setBright(Double.parseDouble(bright)); // 문자열을 double로 데이터 타입을 변환함 
	    moodLamp.on();

	}

}

// Run 버튼의 팝업 버튼을 클릭하여 Run Configurations 메뉴를 클릭
// Argument 탭에서 Program arguments에 원하는 값을 입력 - 아규먼트를 입력하게 되면 main 메소드의 args 파라미터는 아규먼트 값을 받아서 동작하게 된다

// args - 문자열 배열로 여러 개의 String 데이터가 들어있을 수 있음, 인덱스를 통해 배열의 데이터를 꺼내 쓸 수 있고, 인덱스는 0부터 시작함

// 이클립스 없이 자바로 프로그래밍하는 법을 배워보기
// PATH (환경변수)- 디렉터리 경로의 목록
// 직접 컴파일 실행하는 방법을 보았음


5/5 5일차

// 자바의 라이브러리 도구 - System, Data, Math, PrintWriter 등이 있음
// 작업들의 시간적 순서에 주목해서 우리는 Program이라고 부르고, 도구의 응용에 주목해서 우리는 Application이라고 부름
// 자바 API(Application Programming Interface) -  자바의 도구들을 응용해서 사용하기 위해서 일정한 조작 장치를 구성, 자바 프로그램은 또 다른 자바 프로그램에서 사용될 수도 있고,다른 프로그램에서 사용할 수 있도록 만들어둔 장치
// UI(User Interface) - 사용자가 자바 프로그램을 사용할 수 있도록 만들어둔 장치 (예: 커맨드 라인 시스템의 아규먼트, 데스크톱 앱의 버튼, 웹 페이지의 링크 등)

// Java API documentation 보는 방법 
// 포털검색을 통해 Java API documentation 페이지를 열기 - 왼쪽 위 : 패키지들에 대한 정보, 왼쪽 아래 : 클래스에 대한 정보
// Math 클래스 안에는 PI와 같은 변수, floor,ceil과 같은 메소드들이 포함되어 있음 패키지는 이러한 클래스들을 하나의 묶음으로 정리한 것

public class ClassApp {

	public static void main(String[] args) {
		
		System.out.println(Math.PI);
		System.out.println(Math.floor(1.6));
		System.out.println(Math.ceil(1.6));

	}

}

// Math 클래스에는 수학과 관련된 여러 변수들과 메소드들이 있음
// PI 변수는 원주율이 적절한 정밀도로 저장되어 있는 변수
// floor 메소드는 특정 소수점 이하에 대해서 버림한 값을 산출
// ceil 메소드는 특정 소수점 이하에 대해서 올림한 값을 산출

import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;
public class InstanceApp {

	public static void main(String[] args) throws IOException{
		
		PrintWriter p1 = new PrintWriter("result1.txt");
		p1.write("Hello 1");
		p1.close();
		
		PrintWriter p2 = new PrintWriter("result2.txt");
		p2.write("Hello 2");
		p2.close();
		System.out.println(p1.toString());
		p2.toString();
		p2.write("Hello 2");
		
		
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
//		PrintWriter.write("result1.txt", "Hello 1");	
//		PrintWriter.write("result2.txt", "Hello 2");
	}

}

// 인스턴스를 만드는 이유
// 인스턴스를 만들지 않고 PrintWriter.weite("파일이름", "쓸 내용"); 이렇게 구현하면? - 여러 파일에 반복적으로 여러 내용을 쓰는 상황이리고 가정 -> 한번 파일에 쓰기 작업을 수행할 떄마다 일일이 파일의 이름을 입력해 줘야 한다는 단점이 있음
// 인스턴스는 객체를 다양한 상태에서 사용하고, 기능을 재사용할 경우가 많은 상황에서 유용한 방식임

// 클래스의 상속관계 - 클래스 간에는 서로 계층적인 관계를 갖고 있을 수 있음
// 클래스 간의 상속관계의 특성 - 자식에 해당하는 클래스는 부모에 해당하는 클래스의 모든 변수와 메소드를 사용할 수 있음
// Open Type hierarchy : 이클립스 안에서 클래스의 상속관계 확인 가능

// 나의 앱 만들기

public class AccountingApp {

	public static void main(String[] args) {
		
		System.out.println("Value of supply : "+12345.0);
		System.out.println("VAT : "+ (12345.0*0.1));
		System.out.println("Total : "+ (12345.0 + 12345.0*0.1) );
		System.out.println("Expense : "+ (12345.0*0.3) );
		System.out.println("Income : "+ (12345.0 - 12345.0*0.3) );
		System.out.println("Dividend 1 : "+ (12345.0 - 12345.0*0.3) * 0.5 );
		System.out.println("Dividend 2 : "+ (12345.0 - 12345.0*0.3) * 0.3 );
		System.out.println("Dividend 3 : "+ (12345.0 - 12345.0*0.3) * 0.2 );

		// Edit - find/replace 기능을 사용하여 가격을 바꿀 수 있음
		// 위는 find/replace 기능으로 10000.0 -> 12345.0 으로 바꾼 것임

	// 변수도입

public class AccountingApp {

	public static void main(String[] args) {

		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply * expenseRate;
		double income = valueOfSupply - expense;
		double dividend1 = income * 0.5;
		double dividend2 = income * 0.3;
		double dividend3 = income * 0.2;

		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
		System.out.println("Expense : " + expense);
		System.out.println("Income : " + income);
		System.out.println("Dividend 1 : " + dividend1);
		System.out.println("Dividend 2 : " + dividend2);
		System.out.println("Dividend 3 : " + dividend3);

	}

}

// 특정 값을 지역 변수로 바꾸는 방법
// 특정 값을 블록으로 지정 - Extract Local Variable - Refactor - 변수의 이름을 지정하고 OK 누르기 (OK 옆에 Preview 버튼을 누르면 변수 생성 전후를 비교가능)
// 변수로 지정하고자 하는 값을 지우고 이름을 바로 입력하면 이클립스에서 변수 생성을 도와줌 (Create local variable 'expenseRate')

// 아규먼트를 받는 프로그램으로 수정하는 방법을 배움


6일차
=============

- 해결하지 못한 불편함을 예견하고 불편함을 해소할 수 있을 만한 도구들을 배워본다

**제어문**
- 프로그램의 실행 과정을 조건에 따라 바꾸는 것
1. 조건문
2. 반복문

**조건문**

*만원보다 큰 경우-5:3:2로 나눔*

public class AccountingIFApp {

	public static void main(String[] args) {

		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply * expenseRate;
		double income = valueOfSupply - expense;
		
		double dividend1 = income * 0.5;
		double dividend2 = income * 0.3;
		double dividend3 = income * 0.2;

		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
		System.out.println("Expense : " + expense);
		System.out.println("Income : " + income);
		System.out.println("Dividend 1 : " + dividend1);
		System.out.println("Dividend 2 : " + dividend2);
		System.out.println("Dividend 3 : " + dividend3);

	}

}

*만원보다 작은 경우-첫번째 사람에게 몰아줌*

public class AccountingIFUnder10000App {

	public static void main(String[] args) {

		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply * expenseRate;
		double income = valueOfSupply - expense;
		
		double dividend1 = income * 1;
		double dividend2 = income * 0;
		double dividend3 = income * 0;

		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
		System.out.println("Expense : " + expense);
		System.out.println("Income : " + income);
		System.out.println("Dividend 1 : " + dividend1);
		System.out.println("Dividend 2 : " + dividend2);
		System.out.println("Dividend 3 : " + dividend3);

	}

}

- if문을 사용하여 하나의 프로그램으로 문제를 해결

public class AccountingIFApp {

	public static void main(String[] args) {

		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply * expenseRate;
		double income = valueOfSupply - expense;
		
		double dividend1;
		double dividend2;
		double dividend3;
		
		if(income > 10000.0) {
			dividend1 = income * 0.5;
			dividend2 = income * 0.3;
			dividend3 = income * 0.2;
		} else {
			dividend1 = income * 1.0;
			dividend2 = income * 0;
			dividend3 = income * 0;
		}

		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
		System.out.println("Expense : " + expense);
		System.out.println("Income : " + income);
		System.out.println("Dividend 1 : " + dividend1);
		System.out.println("Dividend 2 : " + dividend2);
		System.out.println("Dividend 3 : " + dividend3);

	}

}

**배열**


public class AccountingArrayApp {

	public static void main(String[] args) {

		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply * expenseRate;
		double income = valueOfSupply - expense;
		
        double[] dividendRates = new double[3];
        dividendRates[0] = 0.5;
        dividendRates[1] = 0.3;
        dividendRates[2] = 0.2;
        
		double dividend1 = income * dividendRates[0];
		double dividend2 = income * dividendRates[1];
		double dividend3 = income * dividendRates[2];

		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
		System.out.println("Expense : " + expense);
		System.out.println("Income : " + income);
		System.out.println("Dividend 1 : " + dividend1);
		System.out.println("Dividend 2 : " + dividend2);
		System.out.println("Dividend 3 : " + dividend3);

	}

}

- 프로그램의 기능은 변하지 않았지만, 배열로 묶어서 표현함으로써 각각의 값들이 연관된 정보라는 것을 분명히 할 수 있게 되었고, 변수의 개수도 줄어들게 되었음

**반복문**

- 배열과 반복문을 함께 활용하면 프로그램을 훨씬 간결하게 만들 수 있음

public class AccountingArrayLoopApp {

	public static void main(String[] args) {

		double valueOfSupply = Double.parseDouble(args[0]);
		double vatRate = 0.1;
		double expenseRate = 0.3;
		double vat = valueOfSupply * vatRate;
		double total = valueOfSupply + vat;
		double expense = valueOfSupply * expenseRate;
		double income = valueOfSupply - expense;
		
		

		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + vat);
		System.out.println("Total : " + total);
		System.out.println("Expense : " + expense);
		System.out.println("Income : " + income);
		
		double[] dividendRates = new double[3];
		dividendRates[0] = 0.5;
		dividendRates[1] = 0.3;
		dividendRates[2] = 0.2;
		
			
		int i = 0;
		while(i < dividendRates.length) {
			System.out.println("Dividend : " + (income*dividendRates[i]) );
			i = i + 1;
		}
		

	}

- While문을 이용하여 반복적으로 동작하던 작업을 간결하게 바꾸어봄

**메소드**
- 메소드는 클래스의 동작을 나타내는 함수

*만들어진 메소드를 실행하는 코드(괄호안의 값은 입력값)*
		double vat = getVAT(valueOfSupply, vatRate);

*메소드를 만드는 코드*
	private static double getVAT(double valueOfSupply, double vatRate) {
		return valueOfSupply * vatRate;
	} 

- 메소드를 도입하여 훨씬 더 단정한 코드를 만들 수 있음
- 지역변수를 전역변수로 바꾸면 메소드의 파라미터를 없앨 수 있음

public class AccountingMethodApp {
	public static double valueOfSupply;
	public static double vatRate;
	public static double expenseRate;
	public static void main(String[] args) {
		valueOfSupply = 10000.0;
		vatRate = 0.1;
		expenseRate = 0.3;
		print();
	}

	public static void print() {
		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + getVAT());
		System.out.println("Total : " + getTotal());
		System.out.println("Expense : " + getExpense());
		System.out.println("Income : " + getIncome());
		System.out.println("Dividend 1 : " + getDiviend1());
		System.out.println("Dividend 2 : " + getDiviend2());
		System.out.println("Dividend 3 : " + getDiviend3());
	}

	public static double getDiviend1() {
		return getIncome() * 0.5;
	}
	public static double getDiviend2() {
		return getIncome() * 0.3;
	}
	public static double getDiviend3() {
		return getIncome() * 0.2;
	}

	public static double getIncome() {
		return valueOfSupply - getExpense();
	}

	public static double getExpense() {
		return valueOfSupply * expenseRate;
	}

	public static double getTotal() {
		return valueOfSupply + getVAT();
	} 

	public static double getVAT() {
		return valueOfSupply * vatRate;
	}

}

- main 메소드 안의 동작들은 단순해졌고, 세부적인 동작들은 다른 메소드 안에서 정의되어 프로그램을 사용하는 입장에서 보기 단정한 코드로 바뀜

**클래스**
- 서로 연관된 변수와 메소드를 묶어놓은 것이다
- Window - Show View - Outline 에서 클래스에 포함되어 있는 변수와 메소드들이 정리되어 나타나 있는 것을 알 수 있음

class Accounting{
	public static double valueOfSupply;
	public static double vatRate;
	public static double expenseRate;
	public static void print() {
		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + getVAT());
		System.out.println("Total : " + getTotal());
		System.out.println("Expense : " + getExpense());
		System.out.println("Income : " + getIncome());
		System.out.println("Dividend 1 : " + getDiviend1());
		System.out.println("Dividend 2 : " + getDiviend2());
		System.out.println("Dividend 3 : " + getDiviend3());
	}

	public static double getDiviend1() {
		return getIncome() * 0.5;
	}
	public static double getDiviend2() {
		return getIncome() * 0.3;
	}
	public static double getDiviend3() {
		return getIncome() * 0.2;
	}

	public static double getIncome() {
		return valueOfSupply - getExpense();
	}

	public static double getExpense() {
		return valueOfSupply * expenseRate;
	}

	public static double getTotal() {
		return valueOfSupply + getVAT();
	} 

	public static double getVAT() {
		return valueOfSupply * vatRate;
	}
}
public class AccountingClassApp {
	
	public static void main(String[] args) {
		Accounting.valueOfSupply = 10000.0;
		Accounting.vatRate = 0.1;
		Accounting.expenseRate = 0.3;
		Accounting.print();
		// anotherVariable = ...;
		// anotherMethod = ...;
	}

	

}

- 클래스를 이용해서 프로그램을 정리하는 방법을 알아봄

**인스턴스**
- 클래스를 실제로 실행시킨 실체화된 클래스라고 할 수 있음 이를 통해 다양한 상태에 있는 여러 개의 클래스를 돌릴 수 있음

class Accounting{
	public double valueOfSupply;
	public double vatRate;
	public double expenseRate;
	public void print() {
		System.out.println("Value of supply : " + valueOfSupply);
		System.out.println("VAT : " + getVAT());
		System.out.println("Total : " + getTotal());
		System.out.println("Expense : " + getExpense());
		System.out.println("Income : " + getIncome());
		System.out.println("Dividend 1 : " + getDiviend1());
		System.out.println("Dividend 2 : " + getDiviend2());
		System.out.println("Dividend 3 : " + getDiviend3());
	}

	public double getDiviend1() {
		return getIncome() * 0.5;
	}
	public double getDiviend2() {
		return getIncome() * 0.3;
	}
	public double getDiviend3() {
		return getIncome() * 0.2;
	}

	public double getIncome() {
		return valueOfSupply - getExpense();
	}

	public double getExpense() {
		return valueOfSupply * expenseRate;
	}

	public double getTotal() {
		return valueOfSupply + getVAT();
	} 

	public double getVAT() {
		return valueOfSupply * vatRate;
	}
}
public class AccountingClassApp {
	
	public static void main(String[] args) {
		// instance 
		Accounting a1 = new Accounting();
		a1.valueOfSupply = 10000.0;
		a1.vatRate = 0.1;
		a1.expenseRate = 0.3;
		a1.print();
		
		Accounting a2 = new Accounting();
		a2.valueOfSupply = 20000.0;
		a2.vatRate = 0.05;
		a2.expenseRate = 0.2;
		a2.print();
		
		a1.print();
	}
}

- 클래스를 복사하지 않아도 인스턴스를 만들어서 표현가능


7일차
=============

> 지난 시간 배운 내용 요약
  - 프로그램 : 우리가 원하는 작업들을 시간 순서대로 진행되도록 명령하는 것
  - 조건문 : 조건에 따라서 실행할 작업의 순서를 제어하는 것
  - 반복문 : 같은 작업을 여러 번 반복할 경우 사용되는 것
  - 조건문과 반복문을 위해서는 조건을 구성해야 함 -> 조건을 구성하기 위해서 자바에서는 Boolean 데이터 타입과, 비교 연산 기능을 제공함

**Bloolean Datatype**

- reserved word : true, false 는 변수의 이름으로 사용할 수 없음 (이미 쓰임이있는 키워드들, 앞으로 그럴 가능성이 있는 키워드들 이기 때문) 

package java_flow_control;

public class BooleanApp {

	public static void main(String[] args) {
		
		System.out.println("One");
		System.out.println(1);
		
		System.out.println(true);
		System.out.println(false);
		
		String foo = "Hello world";
		// String true = "Hello world"; reserved word
		
		System.out.println(foo.contains("world"));
		System.out.println(foo.contains("egoing"));

	}

}

*Boolean 데이터 타입*
- 참과 거짓을 표현하는 데이터 타입
- true와 false 키워드를 이용하여 직접 입력할 수도 있고 메소드의 리턴 값이나 비교 연산으로 도출할 수 있음
- 문자열 객체의 contains 메소드와 같이 결과값이 boolean 데이터 타입인 경우, 또는 비교 연산자를 이용해서 계산하는 경우에도 boolean 데이터 타입을 다루게 됨

**비교 연산자**
- 값의 대소, 같음을 비교하는 연산자
- 부등호, 등호와 같은 역할을 함

public class ComparisonOperatorApp {

	public static void main(String[] args) {
		
		
		System.out.println(1 > 1); // false
		System.out.println(1 == 1); // true
		System.out.println(1 < 1); 
		System.out.println(1 >= 1);

	}

}

> 비교 연산자 종류 
  + a > b : a가 b보다 큼
  + a < b : a가 b보다 작음
  + a >= b : a가 b보다 크거나 같음
  + a <= b : a가 b보다 작거나 같음
  + a == b : a가 b와 같음
  + a != b : a가 b와 같지 않음
  (참이라면 true, 거짓이라면 false를 산출)

**if문**
- 제어문의 하나로 조건에 따라 작업을 실행하거나 실행하지 않게 만들어줌

> if문의 구성 요소 
  - if
  - 조건식
  - 코드블럭 (실행할 코드)
  - else if
  - else
  (if와 조건식이 필수 구성 요소, 나머지는 필수요소 아님)
  *조건식에는 boolean 타입만 들어갈 수 있음*

public class IfApp {

	public static void main(String[] args) {
		
		System.out.println("a");
		if(false) {
		    System.out.println(1);
		} else if(true) {
		    System.out.println(2);
		} else {
			System.out.println(3);
		}
		System.out.println("b");
	}

}

* 조건문은 중첩할 수 있고, if와 else는 하나의 조건문에 한 번만 들어갈 수 있지만, else if는 여러 개가 들어갈 수 있음

**조건문 응용1**
- String 클래스의 boolean 리턴 메소드인 equals 메소드를 이용해서 간단한 인증 기능을 구현해봄

package java_flow_control;

public class AuthApp {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		System.out.println("Hi.");
		
		//if(inputId == id) {
		if(inputId.equals(id)) {
			System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}
		

	}

}

- ==와 같은 비교 연산자는 기본 데이터 형과는 달리 문자열과 같은 객체에는 의도치 않은 결과를 가져올 수 있음 그래서 문자열이 서로 같은지를 비교하기 위해서 String 객체에서는 equals 메소드를 제공하고 있음
- 조건식을 비교 연산자나 메소드를 통해 구성하게 되면, 미리 정해놓은 조건이 아니라 *프로그램이 돌아가는 동안*에 정해진 조건에서 특정 작업을 실행할 수 있게 함

**조건문 응용2**

*맥에서 주석처리 하는 방법 - command + /*

package java_flow_control;

public class AuthApp {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String inputPass = args[1];
		
		System.out.println("Hi.");
		
		//if(inputId == id) {
//		if(inputId.equals(id)) {
//			if(inputPass.equals(pass)) {
//			    System.out.println("Master!");
//		    } else {
//			    System.out.println("Wrong password!");
//		    }
//		} else {
//			System.out.println("Who are you?");
//		}
		
		if(inputId.equals(id) && inputPass.equals(pass)) {
			System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}
		

	}

}
* 아이디와 패스워드가 모두 같은지 확인하기 위해서는 AND 연산자 사용

- 여러 개의 boolean 데이터에 대해 모두 혹은 일부가 참인지 알아보려면? -> 조건 연산자 사용

*조건 연산자의 종류*
- &&(AND)
- ||(OR)
* && 연산자는 전항과 후항이 모두 참일 경우에만 참을 반환, 아니면 거짓을 반환
* || 연산자는 전항과 후항 중 하나라도 참일 경우에 참을 반환, 모두 거짓일 때에만 거짓을 반환
* && 연산자는 || 연산자보다 우선순위가 높음

**== VS equals**

*원시 데이터 타입*
- boolean, byte, char, short, int, long, float, double (8개)
- 원시 데이터 타입의 변수는 선언되면 메모리(Stack)에 공간이 할당되며, 그 메모리 공간 안에 실제 값이 들어가게 됨
- 원시 데이터의 경우 == 연산자는 변수가 가리키는 값을 토대로 비교하게 됨

*원시 데이터 타입이 아닌 것*
- java.lang.Object 클래스를 비롯해 여기에서 파생된 다른 모든 클래스들
- 클래스는 new 키워드를 통한 인스턴스가 만들어지는 시점에 또다른 메모리 구역(Heap)에서 새로운 공간을 할당하여 값을 저장하고 변수는 그 값이 저장된 메모리의 주소를 가리키게 됨
- 인스턴스 간 == 연산자를 이용할 경우 그 메모리의 주소를 비교하게 됨

*문자열 리터럴과 같은 방식으로 문자열을 생성한 경우*
String s3 = "JAVA";
String s4 = "JAVA";
- 문자열 리터럴로 문자열을 생성할 때, 이미 같은 문자열을 생성한 적이 있다면(s4의 경우) 새로 메모리 공간을 할당하지 않고, 새로운 변수는 기존의 문자열이 저장된 메모리(String Pool(Heap))의 주소를 가리키게 됨
- 이러한 경우 == 연산자를 이용하였을 때 같은 주소를 가리키고 있기 때문에 true가 나오게 됨

> 즉 == 연산자는 변수가 일차적으로 가리키고 있는 메모리 공간의 값을 기준으로 판단함
> 반면 equals 메소드는 구현에 따라 다르지만, 변수가 최종적으로 가리키고 있는 값을 기준으로 판단함

  원시데이터 타입이면 == 이거 쓰면 돼
  원시데이터 타입이 아니면 equals 쓰거나 객체가 서로 같은지 확인하기
  *간단하게 말해*, == 는 같은 곳에 있냐, equals는 내용이 같으냐

**논리 연산자**

public class LogicalOperatorApp {

	public static void main(String[] args) {
		
		System.out.println(1 == 1);
		
		
		// AND
		System.out.println(true && true); // true
		System.out.println(true && false); // false
		System.out.println(false && true); // false
		System.out.println(false && false); //false

		// OR
		System.out.println(true || true); // true
		System.out.println(true || false); // true
		System.out.println(false || true); // true
		System.out.println(false || false); //false
		
		// NOT
		System.out.println(!true); // false
		System.out.println(!false); // true
	}

}

*! 연산자*
- NOT 연산을 수행하고 참, 거짓 값을 반전시킴

public class AuthApp2 {

	public static void main(String[] args) {
		
		String id = "egoing";
		String inputId = args[0];
		
		String pass = "1111";
		String pass2 = "2222";
		String inputPass = args[1];
		
		
		System.out.println("Hi.");
		boolean isRightPass = (inputPass.equals(pass) || inputPass.equals(pass2));
		if(inputId.equals(id) && isRightPass ) {
			System.out.println("Master!");
		} else {
			System.out.println("Who are you?");
		}

	}

}
- 패스워드로 쓸 수 있는 문자열이 1개였지만 2개로 늘어남
- 패스워드가 둘 중 하나만 충족하면 되므로 || 연산자를 이용, 이 조건을 boolean 변수 isRightPass에 할당하여 간결성있게 구성함

**반복문**
- 조건에 따라 특정한 작업을 반복하게 하는 제어문
- while문 for문 등으로 반복문을 구현함

*While문*
- 조건식이 참일 동안에 코드블럭의 작업을 반복함
- 조건식에 true를 입력할 경우 조건이 항상 참이기 때문에 무한으로 반복하게 됨

*For문*
- 조건식이 3개의 부분으로 나뉘어져 있음
1. 변수의 초기화
2. 조건식
3. 1회 반복을 끝내고 수행할 연산
- 각각의 부분은 세미콜론(;)으로 구분되어 있음
- 변수의 초기화는 for문이 시작될 때 한 번만 수행되고, 조건식이 참일 경우에만 반복함
- 1회 반복이 끝나면 (} 부분) 지정한 연산을 처리하고 다시 조건식을 확인하여 반복작업을 실행함

* 변수의 초기화 부분에서 변수를 새로 선언했다면, 그 변수는 for문 안에서만 존재하고 for문을 벗어나면 사라짐

public class LoopApp {

	public static void main(String[] args) {
		
		System.out.println(1);
		System.out.println("=== while ===");
		int i = 0;
		//..
		while(i < 3) {
		    System.out.println(2);
		    System.out.println(3);
//		    i = i + 1;
		    //..
		    i++;
		}
		System.out.println("=== for ===");
	    for(int j=0; j < 3; j++) {
	    	System.out.println(2);
		    System.out.println(3);
		}

		System.out.println(4);

	}

}

**배열**
- 반복문과 같이 사용할 때 사용하기 좋은 데이터 타입
- 같은 데이터를 여러 개 묶어놓은 형태로, 반복되는 작업을 수행할 때 유용하게 사용할 수 있음

public class ArrayApp {

	public static void main(String[] args) {
		
		// egoing, jinhuck, youbin
//		String users = "egoing, jinhuck, youbin";
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		System.out.println(users[1]);
		System.out.println(users.length);
		
		int[] scores = {10, 100, 100}; // 원소, element
		System.out.println(scores[1]);
		System.out.println(scores.length);

	}

}

- 배열을 선언할 때는 변수 타입명 뒤에 빈 [] 대괄호를 입력하고 변수 이름을 입력함
- 초기화를 할 경우에는 new 키워드를 이용하여 [] 대괄호 안에 요소의 개수를 입력함 또는 리터럴로 입력할 수 있는 데이터 타입의 경우, {} 중괄호 안에 요소를 리터럴로 입력할 수 있음

- 배열은 인덱스를 통해 접근하고 인덱스는 [] 대괄호 안에 입력함

**반복문+배열**
- 반복문을 이용하여 배열의 요소들에 대해 같은 작업을 수행하는 프로그램 만들기

public class LoopArray {

	public static void main(String[] args) {
		/*
		 * <li>egoing</li>
		 * <li>jinhuck</li>
		 * <li>youbin</li>
		 */
		
		String[] users = new String[3];
		users[0] = "egoing";
		users[1] = "jinhuck";
		users[2] = "youbin";
		
		for(int i=0; i<users.length; i++) {
			System.out.println(users[i]+",");
		}

	}
}
- 배열도 하나의 객체이기 때문에 여러 필드와 메소드가 담겨 있음
- 그 중 length 필드는 배열의 요소 개수를 담고 있는 필드임 -> 조건식에서 이 필드를 이용하게 되면 직접 배열의 요소 개수를 입력하지 않아도 프로그램을 실행할 때마다 달라질 수 있는 요소의 개수를 반영하여 반복문을 돌릴 수 있음
