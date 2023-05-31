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

### <Setter>
Setter는 원하는 Property의 값을 Set(지정, 설정) 하는 것이다.
``` xml<Setter Property="Background" Value="Blue"/>``` 는 Background 라는 Property의 값(Value)를 Blue로 설정한다는 뜻이다.

## Resources
한 번이상 사용되기를 원하는 자원을 말한다고 한다.
여러번 사용되길 원하는 것들을(예:Style) Resource에 등록해서 사용할 수 있다.
Style을 사용할 때 App.Resource에 등록해서 사용하는 경우가 많은데 꼭 App.xaml에 파일에만 Resuorce를 등록할 수 있는 건 아니다.
Button에도 StackPanel에도 있다. 다만 App.xaml이 최상위 객체이기 때문에 ```xml <Application.Resources> ``` 에 등록하면 전역에서 사용할 수 있다.
즉 Resuorce를 사용할 때 상위객체에 있는 Resource는 다 사용할 수 있다.
