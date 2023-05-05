JAVA Boostcourse
=============
2023-05-01 1일차 스터디
-------------

<pre>
<code>
public class HelloWorldApp {
	public static void main(String[] args) {
		System.out.println("Hello World!!");
	}
}
</pre>
</code>

- 데스크톱 애플리케이션 만들기

	- 기본 코드

<pre>
<code>
import javax.swing.*;   
import java.awt.Dimension;
import java.awt.Toolkit;
public class HelloWorldGUIApp{
    public static void main(String[] args){
        javax.swing.SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                JFrame frame = new JFrame("HelloWorld GUI");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setPreferredSize(new Dimension(400, 300));
                JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER);
                frame.getContentPane().add(label);
                Dimension dim = Toolkit.getDefaultToolkit().getScreenSize();
                frame.setLocation(dim.width/2-400/2, dim.height/2-300/2);

                frame.pack();
                frame.setVisible(true);
            }
        });
    }
}
</pre>
</code>

- 수정해본 코드

<pre>
<code>
JLabel label = new JLabel("Hello World!!", SwingConstants.CENTER);
</pre>
</code>

***

2023-05-02 2일차 스터디
-------------

- Datatype.java

<pre><code>
public class Datatype{
	public static void main(String[] args) {
		System.out.println(6); // number
		System.out.println("six"); // String

		System.out.println("6"); // String

		System.out.println(6+6);
		System.out.println("6+6");
		System.out.println("6"+"6");
		// 양 옆에 문자열이 있을 경우는 더하기가 아닌 결합연산자라는 문자열을 위한 연산이 사용된다
		// 문자열은 곱하기 연산자를 사용할 수 없다

		System.out.println(6*6);

		System.out.println("111".length()); // 문자열의 길이를 알려준다
		System.out.println();
	}
}
</code></pre>

- Number.java

<pre><code>
public class Number {

	public static void main(String[] args) {
		// Operator
		System.out.println(6 + 2);
		System.out.println(6 - 2);
		System.out.println(6 * 2);
		System.out.println(6 / 2);

		// method
		// 메소드는 수학과 관련된 자주 사용되는 것들을 그룹핑해 놓은 캐비냇 같은 것
		System.out.println(Math.PI); // 적당한 정밀도로 보여준다
		System.out.println(Math.floor(Math.PI)); // floor는 수학적으로 내림, 뒤에있는 소수점을 자른다
		System.out.println(Math.ceil(Math.PI)); // ceil은 올림, 3.14에서 그 뒤에 값 1을 올림
		System.out.println(Math.ceil(6.77)); // 7.0

	}

}
</code></pre>

- StringApp.java

<pre><code>
public class StringApp {

	public static void main(String[] args) {

		// Character VS String
		System.out.println("Hello World"); // String, 문자열 = character들이 모여있는 것
		System.out.println('A'); // Character, 문자 = 한 글자만 표현할 때
		System.out.println("A"); // String

		// new line
		System.out.println("Hello "
				+ "World"); // 문자열과 문자열을 더한 것
		System.out.println("Hello \nWorld"); // 줄바꿈

		// escape
		// 역슬래쉬를 통해서 그 뒤에 따라오는 어떤 임무가 있는 문자의 임무를 일시적으로 해방시키는 것
		System.out.println("Hello \"World\""); // \"  \"은 Hello "World"

	}

}
</code></pre>

- Variable.java

<pre><code>
public class Variable {

	public static void main(String[] args) {

		/* 변할 수 있는 문자가 변수
		   변수는 데이터 타입을 지정해줘야 한다
		   변수를 만들 때는 그 변수가 어떤 데이터 타입을 담을 수 있는지 명확하게 표현해줘야 한다 */

		// Number -> interger
		int a = 1; // 정수 1
		System.out.println(a);

		// real number -> double
		double b = 1.1; // 실수 1.1
		System.out.println(b);

		// String
		String c = "Hello World!"; // 문자열
		System.out.println(c);

	}

}
</code></pre>

- Letter.java

<pre><code>
public class Letter {

	public static void main(String[] args) {
		String name = "gyuli";
		System.out.println("Hello, "+name+"... "+name+ "... egoing ... bye..");

		double VAT = 10.0; // 부가가치세
		System.out.println(VAT); // 부가가치세율

		/* 코딩을 하는데 있어서 코드는 나도 보지만 내가 아닌 다른 사람도 보는 것이기 때문에
		   코드를 딱 봤을 때 그 의미를 빨리 파악할 수 있도록 작성하는 것이 중요하다
		   이때 사용하는 가장 중요한 수단 중 하나가 수단이고 변수는 값의 이름을 부여하는 것이다
		   그러므로 좋은 이름을 사용해야 한다 */

	}

}
</code></pre>

- Casting.java

<pre><code>
public class Casting {

	public static void main(String[] args) {

		// casting
		// 데이터 타입을 다른 데이터 타입으로 컨버팅하는 것
		double a = 1.1;
		// 자동으로 1이 double형으로 컨버팅 된 것
		// 손실이 일어나지 않기 때문에 가능하기 때문에 가능한 것
		double b = 1; 
		// 수동으로 한 것 (명시적으로 한 것)
		double b2 = (double) 1;
		System.out.println(b);

		// int c = 1.1; 이렇게 하면 0.1을 잃어버리게 된다

		// Change type of 'd' to 'double'
		double d = 1.1;
		// Add cast to 'int'
		// int 형태로 강제로 바꾸겠다
		// 소수점 밑에 있는 것들이 사라져 손실이 일어난다
		// 그래서 자바에서 자동으로 해주지 않는 것
		int e = (int) 1.1;
		System.out.println(e);

		// 1 to String
		String f = Integer.toString(1);
		System.out.println(f);

		// 변수가 갖고있는 값이 어떤 데이터 타입인지 알려준다
		System.out.println(f.getClass());

	}

}
</code></pre>

- StringOperation.java

<pre><code>
public class StringOperation {

	public static void main(String[] args) {

		// 텍스트가 몇 글자인지 세야되는 경우
		System.out.println("Hello World".length()); // 11 글자

		// name을 gyuli로 바꾸어준다
		System.out.println("Hello, name~ bye!".replace("name","gyuli"));
		System.out.println("Hello, [[[name]]]... bye..".replace("[[[name]]]", "gyuli"));

	}

}
</code></pre>

***

2023-05-03 스터디
-------------

- Program.java

<pre><code>
public class Program {

	public static void main(String[] args) {

		System.out.println(1);
		System.out.println(2);
		System.out.println(3);

		// 하나하나의 기능들을 우리가 하고자 하는 일의 취지에 맞게 배치하면 컴퓨터가 이 작업을
		// 순차적으로 진행해주는 것을 통해서 자동화를 할 수 있다
		// 우리는 프로그래밍이 순차적으로 실행되는 것을 이용해
		// 사람이 잘 못 하는 것들을 기계에게 위임해서 자동화 할 수 있다는 효과를 얻을 수 있다
	}

}
</code></pre>

- OkJavaGoInHome.java

<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHome {

	public static void main(String[] args) {

		String id = "JAVA APT 507";

		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		// id는 나의 주소
		// 엘리베이터가 어디에 있는지를 알아야 거기 있는 엘리베이터를 제어할 수 있다
		// 자바 아파트에 있는 엘리베이터가 12번째 문장이다

		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();

		// Light on
		Lighting hallLamp = new Lighting(id+ " / Hall Lamp");
		hallLamp.on();

		Lighting floorLamp = new Lighting(id+ " / floor Lamp");
		floorLamp.on();

	}

} // 자동화의 열쇠가 프로그래밍이다
</code></pre>

- 디버거

  버그는 우리가 짠 코드의 의도하지 않은 문제를 말한다.

  그 버그를 잡는 행위를 디버깅이라 하고 디버깅을 할 때 사용하는 도구를 디버거라 부른다.

  현대적인 개발 도구들은 내부적으로 디버거를 가지고 있다.

- 프로그램이 실행되는 것을 멈추고 싶을 때:

  멈추고 싶은 곳에서 더블 클릭을 한다 그러면 점이 생기는데 이 점을 breakpoint라 한다.

  그리고 벌레버튼을 누른다.

  그럼 화면 구성이 바뀌고 중지된 상태로 화면이 멈춘다.

  디버거를 이용하면 프로그램을 한줄한줄 실행시킬 수 있고(Step Over) 실행되는 그 순간에 애플리케이션 내의 변수의 상태를 하나하나 체크할 수 있다.

  디버거를 끝내고 싶을 땐 빨간색 버튼의 터미네이터를 클릭하고 우측 상단에 J(java) 버튼을 클릭한다.

	***

2023-05-04 4일차 스터디
-------------

- 프로그램은 들어오는 정보인 입력을 처리해서 출력을 만들어내는 기계이다.

- input(입력값):

  Argument(프로그램을 실행할 때 텍스트 정보를 주는 것), File, Network, Audio, Program

- output(결과): Monitor, File, Audio, Program

- OkJavaGoInHomeInput.java

<pre><code>
import javax.swing.JOptionPane;

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OkJavaGoInHomeInput {
	
	// parameter, 매개변수 = args에 사용자가 입력한 값이 들어올 것이다
	// 문자열 뒤에 대괄호를 붙이면 문자열로만 이루어져 있는 배열이라는 데이터
	public static void main(String[] args) {
		
		// String id = JOptionPane.showInputDialog("Enter a ID");
		String id = args[0];
		//String bright = JOptionPane.showInputDialog("Enter a Bright level");
		String bright = args[1];
		// 창을 만들어낸다

		// Elevator call
		Elevator myElevator = new Elevator(id);
		myElevator.callForUp(1);
		
		// Security off
		Security mySecurity = new Security(id);
		mySecurity.off();
		
		// Light on
		Lighting hallLamp = new Lighting(id+ " / Hall Lamp");
		hallLamp.on();
		
		Lighting floorLamp = new Lighting(id+ " / floor Lamp");
		floorLamp.on();
		
		DimmingLights moodLamp = new DimmingLights(id+ " moodLamp");
		moodLamp.setBright(Double.parseDouble(bright));
		// bright는 String이지만 입력값으로 들어온 문자가 double 형으로 바뀐다
		moodLamp.on();
	}

} 
</code></pre>

- Runconfiguration

  입력값을 줄 때 Arguments에 값을 입력하면 된다.

  여러개의 값을 줄 땐 “입력값1” “입력값2” ...

  Arguments를 입력하게 되면 main 메소드의 args parameter는 argument 값을 받아서 동작한다.

- args

  문자열 배열(array)로 여러 개의 String 데이터가 들어올 수 있다.

  인덱스 0번부터 시작한다. ( args[0] )

- cmd
	- 외부 라이브러리도 포함해서 컴파일하기

	<pre><code>
	javac -cp ";lib" OkJavaGoInHome.java
	</code></pre>

	- 외부 라이브러리도 포함해서 실행하기

	<pre><code>
	java -cp ";lib" OkJavaGoInHome
	</code></pre>

	- 직접 컴파일 실행

	<pre><code>
	javac OkJavaGoInHomeInput.java
	java OkJavaGoInHomeInput "JAVA APT 707" 15.0
	// 띄어쓰기로 파라미터를 구분한다
	</code></pre>
	

