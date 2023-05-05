//변수의 정의, 정 int에서는 정수가 
public class variable {

    public static void main(String[] args) {

      int a=1; // number -> integer ... -2, -1, 0, 1, 2 ... 정수 데이터 integer를 이용해서 정수 표현
      System.out.println(a);
      double b=1.1; // real number -> double = (실수값이 올수있다) ... -2.0, -1.0, 0, 1.0, 2.0 ...
      System.out.println(b);
      String c = "Hello World"; // 문자열 데이터 string 선언
      System.out.println(c);                          
    }
}
// 변수의 효용 //
public class letter{

    public static void main(String[] args){
        String name = "leezche"; // name이라는 변수를 지정해주면, 자주 사용하는 데이터를 여러번 재사용 가능(변수의 재사용)
        System.out.println("Hello, "+name+"..."+name+" ... egoing ... bye");

        double VAT = 10.0; // VAT(부가가치세)라는 이름을 붙이게 되면, 단순히 실수 10이 아닌 '부가가치세'라는 의미, 코드의 의미를 쉽게 파악
        System.out.println(VAT); // 코드의 가독성
    }
}
//데이터 타입의 변환
public class Casting {

    public static void main(String[] args) {
//정수와 실수 간에 변환하기
        double a = 1.1; //명시적으로 데이터 타입 변환을 나타내야됨
        double b = 1;
        double b2 = (double) 1;
        System.out.println(b);

//      int c = 1.1;
        double d = 1.1; //실수 1.1에서 정수로 변환할려면 데이터 타입을 명시적으로 변경해 주어야 함.
        int e = (int) 1.1;
        System.out.println(e);

        //1 to string
        String f = Integer.toString(1); //정수를 문자열로 변환 , integer 객체의 toString를 이용하면 숫자를 문자열로 변환 가능 
        System.out.println(f.getClass());
    }
}
//프로그래밍이란 무엇인가 ?
//프로그램 = 순서를 나타내는 것 , 컴퓨터 프로그래밍으로 사람이 잘 못하는 일을 기계에서 위임하여 자동화할 수 있다.
public class Program{

    public static void main(sting[] args){

        System.out.println(1);
        System.out.println(2);
        System.out.println(3);
    }
}
//프로그램 만들기 - IoT 라이브러리 만들기 , IoT 프로그램 만들기
//import 구문을 이용해서 org.opentutorials.Elevator를 입력해야 되는 구문을 Elevator로 단순하게 할 수 있다!
import  org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;

public class OKjavaGoInHome {

    public static void main(String[]args){
        String id = "JAVA APT 507"; // 반복적으로 사용되는 값의 경우는 변수로 지정하여 재사용함(코드의 가독성 높임)

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

    }
}
//디버거
//본인의 코드를 분석하고 싶을 때 이용하는 것 : 디버거
//브레이크 포인트

//입력과 출력 1,2 - arguments & parameter
import javax.swing.JOptionPane; // JOptionpane 객체의 showInputDialog 메소드를 이용하면 id 값을 입력 가능하다.

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoInHomeInput {

    public static void main(String[]args){
        String id = JOptionPane.showInputDialog("Enter a ID");
        string bright = JOptionPane.showInputDialog("Enter a Bright level"); //밝기 값 입력
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

        DimmingLights moodLamp = new DimmingLights(id+"moodLamp"); 
        moodLamp.setbright(Double.parseDouble(bright)); //setbright 메소트의 밝기는 double 데이터로 타입 변환을 해야됨.
        moodLamp.on();

        DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
        moodLamp.setBright(10);
        moodLamp.on(); // 밝기 10으로 조절한 것
    }
}

input -> program -> output == 입력정보를 받아서 출력을 하는 것!

import javax.swing.JOptionPane; // JOptionpane 객체의 showInputDialog 메소드를 이용하면 id 값을 입력 가능하다.

import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
public class OKjavaGoInHomeInput {
//parameter, 매개변수
    public static void main(String[]args){
        String id = args[0];
        String bright = args[1];
        // args parameter는 argument의 값을 받아서 동작, 인덱스를 통해 배열의 데이터를 꺼내 쓸수 있고, 인덱스는 0번부터 시작 ! //
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

        DimmingLights moodLamp = new DimmingLights(id+"moodLamp"); 
        moodLamp.setbright(Double.parseDouble(bright)); 
        moodLamp.on();

        DimmingLights moodLamp = new DimmingLights(id+" moodLamp");
        moodLamp.setBright(10);
        moodLamp.on(); 
    }
}
//argument를 입력받아 프로그램 실행시키기
main 메소드의 args 파라미터를 이용하여 입력값을 받는 방법이 있다.

// 직접 컴파일 - 실행
'이클립스는 자바로 프로그램을 만들기 위해 유용한 도구'
이클립스 없이 자바로 프로그래밍을 하려면 우선 자바 파일을 스스로 컴파일할 수 있어야 한다.
그리고 컴파일한 클래스 파일을 실행하는 과정을 거쳐야 한다.
Compile , Run , Input

// 직접 컴파일 - 실행 - 실행환경 살펴보기
// 터미널 열기 //
window : 윈도우 키 + R로 실행 창을 키고, cmd를 입력하여 명령 프롬프트를 실행한다.
MacOS: 스포트라이트에서 terminal을 입력해서 터미널을 실행한다.

// javac 확인 //
터미널에 javac를 입력하고 실행하면 javac 명령어의 사용 방법이 출력된다.
//Windows 자바 확인
자바의 설치 경로(ex: C:\Program files\java\jdk-14.0.1)\bin\javac.exe
// 환경 변수 경로 //
내 pc 오른쪽 클릭 -> 속성 클릭 => 고급 시스템 설정 클릭 -> 환경 변수 클릭 -> path 더블클릭해서 수정 가능

// 직접 컴파일 - 실행 - 컴파일과 실행하기
cd 명령어를 통해 프로젝트 디렉토리로 이동한다.
// 자바 파일 컴파일하기 // 
터미널에 javac를 입력하면 javac 명령어의 사용 방법을 보여준다.
javac Program.java
입력하면 Program.class가 생성된 것을 확인할 수 있다.
javac -cp "." Program.java
(에러가 난다면 위의 코드로 해보기)
// 실행하기 //
java 명령어 이용해서 입력
java Program
(에러가 난다면 아래의 코드로 해보기)
java -cp "." Program

이렇게 해서 파일을 컴파일해서 실행까지 해보는 시간이였다.

//직접 컴파일 - 실행 - 라이브러리이용
//라이브러리를 이용하는 프로그램을 컴파일하기

// OKjavaGoInHome.java 파일 컴파일
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHome {
 
    public static void main(String[] args) {
         
        ....
    }
 
}
//외부 라이브러리도 포함해서 컴파일하기 위해서는 javac 명령어의 옵션 중 --class-path(-cp) 옵션을 이용해서 외부 라이브러리도 함께 지정해야 한다.//
javac -cp ".;lib" OkJavaGoInHome.java 로 입력
macOS나 Linux의 경우에는 ".;lib" 부분의 세미콜론(;)을 콜론(:)으로 바꿔서 입력한다.
콜론(:)이나 세미콜론(;)은 구분자의 의미를 가진다.
//외부 라이브러리의 클래스들도 함께 사용하는 프로그램을 실행하기 위해서는
컴파일했을 때와 마찬가지로 --class-path 옵션에 외부 라이브러리도 포함해서 실행해야 한다.//
//윈도우
java -cp ".;lib" OkJavaGoInHome 로 입력

// 직접 컴파일-실행 - 입력과 출력
// OKjavaGoInHomeInput.java 파일 컴파일
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
         
        String id = args[0];
        String bright = args[1];
        
        ....
 
    }
 
}
실행할 때 argument 입력
org.opentutorials.iot 패키지는 다시 lib 폴더 밖으로 꺼낸다.
터미널에서 argument 주기
- 실행할 클래스 파일 이름 다음에 연달아서 입력 -
java OkJavaGoInHomeInput "JAVA APT 507" 15.0
