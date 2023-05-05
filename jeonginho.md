> 2023-05-03
> Chapter 8
>> Chapter 8-1 변수의 정의
<pre><code>
public class Variable {
    public static void main(Static[] args) {
        int a = 1; // a는 정수 1이다.
        System.out.println(a);
        
        int b = 1.1; // 1.1은 정수(x) ERROR.
        double c = 1.1; // 1.1은 실수(o) -> c는 실수 1.1이다.
        System.out.println(c);
        String d = "Hello World"; 
        // "Hello World"는 문자열 d에 저장됨.
        System.out.println(d);
    }
}
</code></pre>
# 결과 : 1, 1.1, Hello World
>> Chapter 8-2 변수의 효용
<pre><code>
public class Letter {
    public static void main(String[] args) {
        String name = "leezche"; 
        // "leezche"는 문자열 name에 저장됨
        System.out.println("Hello, "+name+" ... "+name+" ... egoing ... bye");
        double VAT = 10.0;
        System.out.println(VAT);
    }
}
</code></pre>
# 결과 : Hello, leezche ... leezche ... egoing ... bye
>> Chapter 8-3 데이터 타입의 변환 - casting
<pre><code>
public class Casting {
    public static void main(String[] args) {
        double a = 1.1;
        double b = 1; 
        // 정수 1을 실수 1로 바꾸고 b에 담아서 출력 시 1.0이 나옴, 손실이 일어나지 않음
        double b2 = (double) 1; 
        // 강제로 1을 실수로 변환하여 1.0 출력.
        System.out.println(b);
        int c = 1.1; 
        // ERROR. 
        double d = 1.1;
        int e = (int)1.1; 
        // 강제로 1.1을 정수로 변환하여 1 출력, 손실이 일어남
        
        System.out.println(e);
        String f = Integer.toString(1); 
        // 1이 출력 되지만 실제로 1은 문자열이다.
        System.out.println(f.getClass()); 
        // .getClass()를 이용하여 출력 시 값의 데이터타입을 함께 출력.
    }
}
</code></pre>
# 결과 : 1.0, 1, 1, class java.lang.String
> Chapter 9
>> Chapter 9-1 프로그래밍이란 무엇인가
<pre><code>
public class Program {
    public static void main(String[] args) {
         
        System.out.println(1); // 1 출력
        System.out.println(2); // 2 출력
        System.out.println(3); // 3 출력
    }
}
</code></pre>
# 결과 : 1, 2, 3
> 프로그래밍을 하는 이유는 자동화 하기 위함.
> 컴퓨터 프로그래밍을 이용하여 사람이 잘 못하는 일을 기계에게 위임하여 자동화할 수 있음. (이런 작업을 하는 언어중 가장 유명한 언어가 JAVA.)
>> Chapter 9-2 프로그램 만들기 - IoT 라이브러리 설치하기
<pre><code>
public class programming {   
}
</code></pre>
> 방법 : iot 사물을 제어할 수 있는 프로그램을 작성하기 위해서 외부 패키지를 다운받아 org 폴더를 programming 프로젝트에 드래그 앤 드랍 시킨다.
>> Chapter 9-3 IoT 프로그램 만들기
<pre><code>
import org.opentutorials.iot.Elevator; 
// org폴더 > opentutorials > iot > Elevator를 import 함. 
import org.opentutorials.iot.Lighting;
// org폴더 > opentutorials > iot > Lighting를 import 함.
import org.opentutorials.iot.Security;
// org폴더 > opentutorials > iot > Security를 import 함.
public class programming {
    public static void main(String[] args) {
        String id = "JAVA APT 507"; 
        // 동작은 같지만 중복이 제거됨.
         
        // Elevator call 
        Elevator myElevator = new Elevator(id);
        // Elevator는 데이터 타입, myElevator는 변수
        myElevator.callForUp(1); 
        // 1층으로 엘레베이터를 보내라는 명령문
         
        // Security off 
        Security mySecurity = new Security(id);
        mySecurity.off();
         
        // Light on
        Lighting hallLamp = new Lighting(id+" / Hall Lamp");
        hallLamp.on();
        //hallLamp 의 불을 킨다.
         
        Lighting floorLamp = new Lighting(id+" / floor Lamp");
        floorLamp.on();
        //floorLamp 의 불을 킨다.
    }
}
</code></pre>
# 결과 : JAVA APT 507 -> Elevator callForUp stopFloor : 1
# JAVA APT 507 -> Security off
# JAVA APT 507 / Hall Lamp -> Lighting on
# JAVA APT 507 / floorLamp -> Lighting on
> Chapter 10 - 디버거
>> 이클립스에서 디버그 하는 방법은 우측상단 Run java 버튼 옆 아래 화살표를 눌러 Debug java를 클릭하면 된다.
>> 이클립스에서 브레이크 포인트를 지정하는 방법은 코드 편집창에서 줄 번호 왼편을 더블클릭하여 브레이크 포인트를 지정할 수 있다.
>> 브레이크 포인트를 지정하고 디버거를 실행하면 브레이크 포인트까지 코드가 실행되며 그 이후로 실행이 정지된다.
>> 브레이크 포인트를 해제 하는 방법은 지정했던 브레이크 포인트를 다시 클릭하면 해제할 수 있다.
>> 이클립스에서 우측의 Variable 탭에서 변수들을 확인할 수 있다.
>> Step Into 버튼을 클릭하면 코드의 자세한 실행과정(메소드)를 볼 수 있다.
>> 다시 원래의 코드로 돌아가고자 할 경우에는 Step Return 버튼을 클릭하여 돌아갈 수 있다.

>8, 9, 10 ENDS

> 2023-05-04
>> 11강, 12강 스터디 내용

> Chapter 11-1 입력과 출력
<pre><code>
import javax.swing.JOptionPane; 
// javax.swing에 속해있는 JOptionPane이 로드되었다.
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
    public static void main(String[] args) {
         
        String id = JOptionPane.showInputDialog("Enter a ID");
        // 이름 입력 (showInputDialog)
        String bright = JOptionPane.showInputDialog("Enter a Bright level");
        // 밝기 입력 (showInputDialog)

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
        moodLamp.setBright(Double.parseDouble(bright));
        //Double.parseDouble()시 double형으로 변환 됨.
        moodLamp.on();
    }
}
</code></pre>

# 입력 : JAVA APT 1004, 10
# 결과 : JAVA APT 1004 -> Elevator callForUp stopFloor : 1
# JAVA APT 1004 -> Security off
# JAVA APT 1004 / Hall Lamp -> Lighting on
# JAVA APT 1004 / floorLamp -> Lighting on
# JAVA APT 1004 moodLamp -> DimmingLights bright : 10.0
# JAVA APT 1004 moodLamp -> Lighting on
> Chapter 11-2 입력과 출력 - arguments & parameter
<pre><code>
import javax.swing.JOptionPane; 
// javax.swing에 속해있는 JOptionPane이 로드되었다.
 
import org.opentutorials.iot.DimmingLights;
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHomeInput {
 
    public static void main(String[] args) {
        //args()는 매개변수이다.(patameter)
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
        moodLamp.setBright(Double.parseDouble(bright));
        //Double.parseDouble()시 double형으로 변환 됨.
        moodLamp.on();
    }
}
</code></pre>

>> argument는 사용자 입력을 의미하는 문자열 배열이다.

>> parameter는 함수에서 전달되어서 사용되는 변수이다.

>> argument는 main()함수의 매개변수로 작용한다.

>> 196줄에 브레이크를 걸고 디버그 시키면 vscode 기준 왼편에 VARIABLES.Local 창이 뜨고 그 속에 args, id, bright에 할당한 값이 보인다.

<pre><code>
first(a,b);
return;

a,b("parameter","argument")
</code></pre>
>> 위 코드에서 a,b는 parameter이다.

>> 위 코드에서 "parameter","argument"는 argument이다.

> Chapter 12-1 직접 컴파일 - 실행 - 소개
>> 이클립스,vscode 없이 혼자 컴파일하기

>> 1. 자바 확장자가 붙은 소스코드를 Class확장자가 붙은 실행파일로 바꾼다 (Compile)

>> 2. 클래스 확장자가 붙은 파일을 실행한다(Run)

>> 3. 실행할 때 입력값을 준다 (Input)

> Chapter 12-2 직접 컴파일 - 실행 - 실행환경 살펴보기
>> 직접 컴파일을 하기 위해 자바의 설치경로를 알고 있어야 한다.

>> 터미널 열기 Window - 윈도우키 + R키로 실행창을 키고, cmd를 입력하여 명령프롬프트를 실행한다.

>> 컴파일, 실행을 하기 위해선 명령 프롬프트에 javac을 입력하여 컴파일 할 수 있다.

>> 자바의 설치경로(C:\Program Files\Java\jdk-17\bin\javac.exe)

>> 환경 변수는 윈도우 탐색기에서 내 PC 항목을 오른쪽 버튼으로 클릭하여 나오는 팝업창에 속성을 클릭한다. 이후 고급시스템 설정을 클릭하고 환경 변수를 클릭하면 환경 변수 목록을 확인할 수 있다. 목록 중 Path를 더블클릭하면 수정 할 수있다.

>> Path는 디렉터리 경로의 목록. 사용자가 전체 경로를 지정하지 않고 명령을 입력하면 목록을 확인하여 해당 명령어가 경로에 속하는지를 살펴본다. 이 과정을 통하여 어떠한 경로든 해당 명령어로 실행 파일을 실행할 수 있다.

> Chapter 12-3 직접 컴파일 - 실행 - 컴파일과 실행하기

>> 명령 프롬프트에서 소스 코드가 위치한 경로를 붙여넣기 한다. (ex)cd C:\Users\egoing\Desktop\java1\Programming

>> dir 명령어로 프로젝트 디렉토리 내부 구조를 확인할 수 있다.

>> 터미널에 javac를 입력하면 javac 명령어의 사용 방법을 보여준다.

>> javac Program.java 를 입력하여 Program.java를 컴파일한다. 에러가 날 시 javac -cp "." Program.java를 입력한다.

>> 컴파일된 클래스 파일을 실행하는 방법은 java Program을 입력한다. 에러가 날 시 java -cp "." Program 을 입력한다.

> Chapter 12-4 직접 컴파일 - 실행 - 라이브러리이용
<pre><code>
import org.opentutorials.iot.Elevator;
import org.opentutorials.iot.Lighting;
import org.opentutorials.iot.Security;
 
public class OkJavaGoInHome {
 
    public static void main(String[] args) {
         
        ....
    }
}
</code></pre>
>> OkJavaGoInHome.java 파일을 컴파일 하기 위해서는 OkJavaGoInHome가 Import 구문을 통해 org.opentutorials.iot 클래스들을 불러들이고 있어서 컴파일을 실행할 때 자동적으로 org.opentutorials.iot의 Elevator, Lighting, Security 클래스들도 컴파일한다. 이때 lib 폴더를 새로 만들어서 org 폴더를 lib 폴더 내부로 이동시킨다.

>> org.opentutorials.iot 패키지는 lib 라이브러리의 일부가 되었다. 그렇기 때문에 OkJavaGoInHome.java 파일은 제대로 실행되지 않는다.

>> 외부 라이브러리도 포함해서 컴파일 하기 위해서는 명령 프롬프트에서 javac -cp ".;lib" OkJavaGoInHome.java 명령어를 입력한다.

>> 외부 라이브러리도 포함해서 실행하려면 java -cp ".;lib" OkJavaGoInHome 명령어를 입력한다.

>> 1. 라이브러리란 다른 사람들 만들어 놓은 여러 유용한 기능을 모아둔 클래스의 집합.
>> 2. 패키지는 특정한 기능들을 모아둔 더 작은 단위의 집합.

> Chapter 12-5 직접 컴파일 - 실행 - 입력과 출력

<pre><code>
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
</code></pre>
>> org.opentutorials.iot 패키지는 다시 iot 폴더 밖으로 꺼낸다.

>> 터미널에서 javac OkJavaGoInHomeInput.java 명령어를 입력하여 컴파일 한다.

>> 터미널에서 아규먼트를 주기 위해서 실행할 클래스 파일 이름다음에 연달아서 입력한다. -> java OkJavaGoInHomeInput "JAVA APT 507" 15.0 (2번째 입력값 15.0은 큰 따옴표 안에 넣어도 되고, 소수점은 생략할 수 있다.)

>> 커맨드 라인에서 우리가 임의값을 추가하여 프로그램을 작동시킨다면 이것만으로 충분히 많은 일을 가치있게 할 수 있다. 

>> 2023-05-04 11,12 END