# WPF Study
## ControlTemplate
- ControlTemplate는 컨트롤의 겉면(XAML로 표현되는)의 형태를 지정할 수 있는 Templeate이다.
- Control 의 Template을 정의한다는 것은, 해당 Control의 기존 xaml 구성을 모두 지우고 다시 그리겠다는 의미다.



## Content



## Style
Control들의 모양을 스타일링 하는 기능이라고 할 수 있다.
Control의 Element에 적용되는 프로퍼티의 집합이라고 볼 수 있고, 이 집합을 Cumtum 할 수 있다.
Style을 이용하면 여러개의 Element를 변경하고 설정할 수 있다.
Ex)
```xml
<Style TargetType="{x:Type Button}" x:Key="ButtonStyle">
  <Setter Property="Background" Value="Blue"/>
  <Setter Property="Foreground" Value="Red"/>
</Style>
```
**TargetType="{x:Type Button}"** 은 Style을 어떤 Control 객체에 적용할 것 인지 정한다.
Button으로 설정했음으로 이 Style은 Button에 적용된다.
**x:Key="ButtonStyle"** 는 Style의 이름 같은 것이다.

```xml
<Button Content="버튼1" Style="{StaticResource ButtonStyle}"></Button>
```
**Style="{StaticResource ButtonStyle}"** 를 보면 StaticResource에 등록 되어있는 ButtonStyle 라는 이름의 Style을 사용한다는 뜻이다.
만약 style의 ```xml x:key=""``` 없이 TargetType만 있으면 전역에 있는 해당 컨트롤에 Style이 적용된다. 
