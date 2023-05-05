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
