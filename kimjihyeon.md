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