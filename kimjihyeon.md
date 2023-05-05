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
