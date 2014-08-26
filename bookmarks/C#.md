# C# TIP

## VisualTreeHelper.GetChildrenCount

VisualTreeHelper.GetChildrenCount(DependencyObject reference) 메소드를 사용하는 중 자식의 수가 0 으로만 나타나는 경우가 있다.  
나의 경우 WPF에서 ListBox에 아이템을 추가한후 child를 확인하는 경우 Window에 위치한 ListBox는 정상적으로 child를 찾았으나 확장성을 위해 Usercontrols로 ListBox를 옮긴후에는 chlid를 계속 찾을수 없었다.  

해결방법은 의외로 간단한데 ListBox의 자식을 찾는 명령을 userconrol의 loaded 이벤트가 완료된 후에 진행하면 정상적으로 찾아진다.  
이런 현상이 발생하는 원인은 VisualTreeHelper.GetChildrenCount은 화면상에 구성된 내용을 가지고 child를 찾는데 객체는 생성하였으나 아직 화면에 나타나지 않은 상태에서 먼저 찾는 경우에 발생되는 현상으로 보인다.  

어차피 VisualTreeHelper.GetChildrenCount은 화면상에 나타난 child를 찾는 메소드이니 loaded 등의 이벤트가 완료된 후에 해당 기능을 실행하면 문제 없을듯 하다.


