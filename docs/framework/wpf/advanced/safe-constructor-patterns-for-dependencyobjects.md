---
title: DependencyObject의 안전한 생성자 패턴
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 6d6ff444b99ca893e687731c56a48ea3ac072dd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187226"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a>DependencyObject의 안전한 생성자 패턴
일반적으로 클래스 생성자는 가상 메서드나 대리자와 같은 콜백을 호출하면 안 됩니다. 이는 생성자는 파생 클래스에 대한 생성자의 기본 초기화로 호출될 수 있기 때문입니다. 특정 개체의 불완전한 초기화 상태에서 가상 항목이 입력될 수 있습니다. 하지만 속성 시스템 자체는 내부적으로 콜백을 종속성 속성 시스템의 일부로 호출하고 표시합니다. 호출을 통해 <xref:System.Windows.DependencyObject.SetValue%2A> 종속성 속성 값을 설정하는 것과 같은 간단한 작업에는 결정의 어딘가에 콜백이 포함될 수 있습니다. 이런 이유로 생성자 본문에서 종속성 속성 값을 설정할 때 주의해야 합니다. 형식이 기본 클래스로 사용될 경우 문제가 발생할 수 있습니다. 종속성 속성 상태 <xref:System.Windows.DependencyObject> 및 여기에 설명된 고유 콜백에 대한 특정 문제를 방지하는 생성자 구현을 위한 특정 패턴이 있습니다.  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a>속성 시스템 가상 메서드  
 다음 가상 메서드 또는 콜백은 종속성 속성 값을 <xref:System.Windows.DependencyObject.SetValue%2A> <xref:System.Windows.ValidateValueCallback> <xref:System.Windows.PropertyChangedCallback> <xref:System.Windows.CoerceValueCallback> <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>설정하는 호출계산 중에 호출될 수 있습니다. 이러한 각 가상 메서드 또는 콜백은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템 및 종속성 속성의 다양성을 확장하기 위한 특정 목적으로 사용됩니다. 이러한 가상 항목을 사용하여 속성 값 확인을 사용자 지정하는 방법에 대한 자세한 내용은 [종속성 속성 콜백 및 유효성 검사](dependency-property-callbacks-and-validation.md)를 참조하세요.  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a>FXCop 규칙 적용 vs. 속성 시스템 가상  
 Microsoft 도구 FXCop를 빌드 프로세스에 사용하고 기본 생성자를 호출하는 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임워크 클래스에서 파생시키거나 파생 클래스에서 자체 종속성 속성을 구현할 경우 특정 FXCop 규칙 위반이 발생할 수 있습니다. 이 위반에 대한 이름 문자열은 다음과 같습니다.  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 이 규칙은 FXCop에 대해 설정된 기본 공용 규칙의 일부입니다. 이 규칙은 최종적으로 종속성 속성 시스템 가상 메서드를 호출하는 종속성 속성 시스템을 통한 추적을 보고할 수 있습니다. 이 규칙 위반은 이 항목에 설명된 권장 생성자 패턴을 따른 후에도 계속 표시될 수 있으므로 FXCop 규칙 집합 구성에서 해당 규칙을 사용하지 않도록 설정하거나 억제해야 할 수 있습니다.  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a>대부분 문제는 기존 클래스를 사용하지 않고 클래스를 파생시킬 경우 발생함  
 이 규칙을 통해 보고된 문제는 생성 시퀀스에서 가상 메서드를 사용하여 구현하는 클래스가 파생될 때 발생합니다. 클래스를 봉인할 경우 또는 클래스가 파생되지 않는지 알거나 파생되지 않도록 하는 경우에는 여기에 설명된 고려 사항과 FXCop 규칙을 유발한 문제가 적용되지 않습니다. 하지만 기본 클래스로 사용되도록 클래스를 작성할 경우(예: 템플릿 또는 확장 가능한 컨트롤 라이브러리 집합을 만들 경우) 여기서 권장된 생성자에 대한 패턴을 따라야 합니다.  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a>기본 생성자는 콜백을 통해 요청된 모든 값을 초기화해야 함  
 클래스 재정의 또는 콜백(속성 시스템 가상 섹션의 목록에서 콜백)에 사용되는 모든 인스턴스 멤버는 해당 값 중 일부가 "실제" 값으로 채워져 있더라도 클래스 매개 변수 없는 생성자에서 초기화되어야 합니다. 매개 변수가 없는 생성자의 매개 변수입니다.  
  
 다음 예제 코드(및 이후 예제)는 이 규칙을 위반하고 문제를 설명하는 의사 C# 예제입니다.  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 응용 프로그램 `new MyClass(objectvalue)`코드가 호출할 때 매개 변수 없는 생성자 및 기본 클래스 생성자가 호출 됩니다. 그런 다음 `Property1 = object1`을 설정하여 `OnPropertyChanged` 가상 메서드를 `MyClass` <xref:System.Windows.DependencyObject>소유로 호출합니다.  재정의는 아직 초기화되지 않은 `_myList`를 참조합니다.  
  
 이러한 문제를 피하는 한 가지 방법은 콜백이 기타 종속성 속성만 사용하고 각 종속성 속성에 설정된 기본값을 등록된 메타데이터로 포함하는지 확인하는 것입니다.  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a>안전한 생성자 패턴  
 클래스가 기본 클래스로 사용될 경우 불완전한 초기화의 위험을 피하려면 다음 패턴을 따릅니다.  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a>기본 초기화를 호출하는 매개 변수 없는 생성자  
 기본 기본값을 호출하는 다음 생성자를 구현합니다.  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a>기본 시그니처와 일치하지 않는 기본값이 아닌(편의) 생성자  
 이러한 생성자가 매개 변수를 사용하여 초기화에서 종속성 속성을 설정하는 경우 먼저 초기화를 위해 고유한 클래스 매개 변수 없는 생성기를 호출한 다음 매개 변수를 사용하여 종속성 속성을 설정합니다. 이러한 속성은 클래스에서 정의된 종속성 속성이거나 기본 클래스에서 상속된 종속성 속성일 수 있지만 두 경우 중 하나에는 다음 패턴을 사용합니다.  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a>기본 시그니처와 일치하는 기본값이 아닌(편의) 생성자  
 동일한 매개 변수화를 사용 하 여 기본 생성자 호출 하는 대신 다시 고유한 클래스의 매개 변수 없는 생성자 호출 합니다. 기본 이니셜라이저를 호출하지 마세요. 대신에 `this()`를 호출해야 합니다. 그 다음에 전달된 매개 변수를 관련 속성을 설정하기 위한 값으로 사용하여 원래 생성자 동작을 재현합니다. 특정 매개 변수가 설정해야 하는 속성을 결정하는 과정의 지침으로 원래 기본 생성자 문서를 사용합니다.  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a>모든 시그니처와 일치해야 함  
 base 형식에 여러 서명이 있는 경우 추가 설정 하기 전에 클래스 매개 변수 없는 생성자 호출의 권장된 패턴을 사용 하는 고유한 생성자 구현과 가능한 모든 서명을 의도적으로 일치 해야 합니다. 속성.  
  
#### <a name="setting-dependency-properties-with-setvalue"></a>SetValue를 사용하여 종속성 속성 설정  
 이러한 패턴은 속성 설정 편의를 위해 래퍼가 없는 속성을 설정하고 <xref:System.Windows.DependencyObject.SetValue%2A>값을 로 설정하는 경우에 적용됩니다. 생성자 <xref:System.Windows.DependencyObject.SetValue%2A> 매개 변수를 통과하는 호출은 초기화를 위해 클래스의 매개 변수 없는 생성자도 호출해야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [사용자 지정 종속성 속성](custom-dependency-properties.md)
- [종속성 속성 개요](dependency-properties-overview.md)
- [종속성 속성 보안](dependency-property-security.md)
