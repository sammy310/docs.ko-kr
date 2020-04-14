---
title: 사용자 지정 컨트롤의 UI 자동화
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: 97db94215220ac2a68e0395bd63b7a874a745a48
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243247"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>WPF 사용자 지정 컨트롤의 UI 자동화
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]에서는 자동화 클라이언트가 다양한 플랫폼 및 프레임워크의 사용자 인터페이스를 검사하거나 운영하는 데 사용할 수 있는 일반화된 단일 인터페이스를 제공합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]를 통해 품질 보증(테스트) 코드 및 화면 읽기 프로그램과 같은 접근성 애플리케이션은 사용자 인터페이스 요소를 검사하고 다른 코드에서 해당 요소에 대한 사용자 상호 작용을 시뮬레이트할 수 있습니다. 모든 플랫폼에서 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 자세한 내용은 접근성을 참조하세요.  
  
 이 항목에서는 WPF 애플리케이션에서 실행되는 사용자 지정 컨트롤에 대한 서버 쪽 UI 자동화 공급자를 구현하는 방법을 설명합니다. WPF는 사용자 인터페이스 요소의 트리에 대응하는 피어 자동화 개체의 트리를 통해 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]를 지원합니다. 접근성 기능을 제공하는 애플리케이션 및 테스트 코드는 자동화 피어 개체를 직접 사용(in-process 코드의 경우)하거나 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]에서 제공하는 일반화된 인터페이스를 통해 사용할 수 있습니다.  

<a name="AutomationPeerClasses"></a>
## <a name="automation-peer-classes"></a>자동화 피어 클래스  
 WPF 컨트롤에서 파생 되는 피어 클래스의 트리를 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] <xref:System.Windows.Automation.Peers.AutomationPeer>통해 지원 합니다. 규칙에 따라 피어 클래스 이름은 컨트롤 클래스 이름으로 시작하고 "AutomationPeer"로 끝납니다. 예를 들어 <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> 컨트롤 클래스의 <xref:System.Windows.Controls.Button> 피어 클래스입니다. 피어 클래스는 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 제어 형식과 거의 동일하지만 WPF 요소에만 해당됩니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 인터페이스를 통해 WPF 애플리케이션에 액세스하는 자동화 코드는 자동화 피어를 직접 사용하지 않지만 동일한 프로세스 공간의 자동화 코드는 자동화 피어를 직접 사용할 수 있습니다.  
  
<a name="BuiltInAutomationPeerClasses"></a>
## <a name="built-in-automation-peer-classes"></a>기본 제공 자동화 피어 클래스  
 요소는 사용자의 인터페이스 작업을 허용하는 경우 또는 화면 읽기 프로그램 애플리케이션 사용자에게 필요한 정보를 포함하는 경우 자동화 피어 클래스를 구현합니다. 일부 WPF 시각적 요소에는 자동화 피어가 없습니다. 자동화 피어를 구현하는 클래스의 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.TextBox>예는 <xref:System.Windows.Controls.Label>에서와 같습니다. 자동화 피어를 구현하지 않는 클래스의 예로는 <xref:System.Windows.Controls.Decorator>에서 <xref:System.Windows.Controls.Border>파생되는 클래스입니다. <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Grid> <xref:System.Windows.Controls.Canvas>  
  
 기본 <xref:System.Windows.Controls.Control> 클래스에는 해당 피어 클래스가 없습니다. <xref:System.Windows.Controls.Control>에서 파생되는 사용자 지정 컨트롤에 해당하는 피어 클래스가 필요한 경우 <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>에서 사용자 지정 피어 클래스를 파생해야 합니다.  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations-for-derived-peers"></a>파생된 피어의 보안 고려 사항  
 자동화 피어는 부분 신뢰 환경에서 실행되어야 합니다. UIAutomationClient 어셈블리의 코드는 부분 신뢰 환경에서 실행되도록 구성되지 않았으며 자동화 피어 코드는 해당 어셈블리를 참조해서는 안 됩니다. 대신 UIAutomationTypes 어셈블리의 클래스를 사용해야 합니다. 예를 들어 UIAutomationClient <xref:System.Windows.Automation.AutomationElementIdentifiers> 어셈블리의 클래스에 해당하는 UIAutomationType 어셈블리의 <xref:System.Windows.Automation.AutomationElement> 클래스를 사용해야 합니다. 자동화 피어 코드에서 UIAutomationTypes 어셈블리를 참조해도 안전합니다.  
  
<a name="PeerNavigation"></a>
## <a name="peer-navigation"></a>피어 탐색  
 자동화 피어를 찾은 후 프로세스 내 코드는 개체 및 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> 메서드를 호출하여 피어 트리를 탐색할 수 있습니다. 컨트롤 내의 WPF 요소 간의 탐색은 피어의 <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> 메서드 구현에 의해 지원됩니다. UI 자동화 시스템은 이 메서드를 호출하여 컨트롤 내에 포함된 하위 요소의 트리를 작성합니다(예: 목록 상자의 목록 항목). 기본 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> 메서드는 요소의 시각적 트리를 트래버스하여 자동화 피어 트리를 빌드합니다. 사용자 지정 컨트롤은 자식 요소를 자동화 클라이언트에 노출하도록 이 메서드를 재정의하여 정보를 전달하거나 사용자 상호 작용을 허용하는 요소의 자동화 피어를 반환합니다.  
  
<a name="Customizations"></a>
## <a name="customizations-in-a-derived-peer"></a>파생된 피어의 사용자 지정  
 보호된 가상 <xref:System.Windows.UIElement> 메서드에서 <xref:System.Windows.ContentElement> <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>파생되고 포함된 모든 클래스. WPF호출은 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 각 컨트롤에 대한 자동화 피어 개체를 가져옵니다. 자동화 코드는 피어를 사용하여 컨트롤의 특성 및 기능에 대한 정보를 가져오고 대화형 사용을 시뮬레이트할 수 있습니다. 자동화를 지원하는 사용자 지정 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 컨트롤은 <xref:System.Windows.Automation.Peers.AutomationPeer>에서 파생된 클래스의 인스턴스를 재정의하고 반환해야 합니다. 예를 들어 사용자 지정 컨트롤이 <xref:System.Windows.Controls.Primitives.ButtonBase> 클래스에서 파생되는 경우 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 반환되는 <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>개체는 에서 파생되어야 합니다.  
  
 사용자 지정 컨트롤을 구현할 때 사용자 지정 컨트롤과 관련된 고유한 동작을 설명하는 "Core" 메서드를 기본 자동화 피어 클래스에서 재정의해야 합니다.  
  
### <a name="override-oncreateautomationpeer"></a>OnCreateAutomationPeer 재정의  
 사용자 지정 <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> 컨트롤에 대한 메서드를 재정의하여 <xref:System.Windows.Automation.Peers.AutomationPeer>에서 직접 또는 간접적으로 파생해야 하는 공급자 개체를 반환합니다.  
  
### <a name="override-getpattern"></a>GetPattern 재정의  
 자동화 피어는 서버 쪽 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 공급자의 몇 가지 구현 측면을 간소화하지만 사용자 지정 컨트롤 자동화 피어는 패턴 인터페이스를 계속 처리해야 합니다. WPF가 아닌 공급자와 마찬가지로 피어는 <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> 네임스페이스에서 와 같은 <xref:System.Windows.Automation.Provider.IInvokeProvider>인터페이스의 구현을 제공하여 제어 패턴을 지원합니다. 컨트롤 패턴 인터페이스는 피어 자체 또는 다른 개체를 통해 구현할 수 있습니다. 피어의 구현은 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 지정된 패턴을 지원하는 개체를 반환합니다. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]코드는 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드를 호출하고 <xref:System.Windows.Automation.Peers.PatternInterface> 열거형 값을 지정합니다. <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 재정의는 지정된 패턴을 구현하는 개체를 반환해야 합니다. 컨트롤에 패턴의 사용자 지정 구현이 없는 경우 이 컨트롤 유형에 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 대해 패턴이 지원되지 않는 경우 기본 형식의 구현을 호출하여 해당 구현 또는 null을 검색할 수 있습니다. 예를 들어 사용자 지정 NumericUpDown 컨트롤을 범위 내의 값으로 설정할 수 있으므로 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 피어가 인터페이스를 <xref:System.Windows.Automation.Provider.IRangeValueProvider> 구현합니다. 다음 예제에서는 피어의 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 메서드가 값에 응답하도록 재정의되는 방법을 보여 주십습니다. <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType>  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 메서드는 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> 하위 요소를 패턴 공급자로 지정할 수도 있습니다. 다음 코드는 <xref:System.Windows.Controls.ItemsControl> 스크롤 패턴 처리를 내부 <xref:System.Windows.Controls.ScrollViewer> 제어의 피어로 전송하는 방법을 보여 주며 있습니다.  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 패턴 처리를 위한 하위 요소를 지정하기 위해 이 코드는 하위 요소 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> 개체를 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 가져옵니다. 하위 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> 요소에 설정하면 하위 요소가 자동화 피어 트리에 나타나지 못하게 하고 하위 요소에 의해 발생하는 모든 이벤트가 <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>에 지정된 컨트롤에서 시작된 것으로 지정됩니다. 컨트롤은 <xref:System.Windows.Controls.ScrollViewer> 자동화 트리에 나타나지 않으며 생성되는 스크롤 이벤트는 <xref:System.Windows.Controls.ItemsControl> 개체에서 시작된 것으로 나타납니다.  
  
### <a name="override-core-methods"></a>"Core" 메서드 재정의  
 자동화 코드는 피어 클래스의 public 메서드를 호출하여 컨트롤에 대한 정보를 가져옵니다. 컨트롤에 대한 정보를 제공하려면 컨트롤 구현이 기본 자동화 피어 클래스에서 제공하는 구현과 다른 경우 이름이 "Core"로 끝나는 각 메서드를 재정의합니다. 최소한 컨트롤은 <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> 다음 예제와 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 같이 메서드및 메서드를 구현해야 합니다.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 구현은 <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> 값을 반환하여 컨트롤을 <xref:System.Windows.Automation.ControlType> 설명합니다. 반환할 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>수 있지만 컨트롤을 정확하게 설명하는 경우 보다 구체적인 컨트롤 형식 중 하나를 반환해야 합니다. 반환 값은 <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> 공급자가 구현하기 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]위해 추가 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 작업이 필요하며 클라이언트 제품은 제어 구조, 키보드 상호 작용 및 가능한 제어 패턴을 예측할 수 없습니다.  
  
 컨트롤에 <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 데이터 콘텐츠가 포함되어 있는지 또는 사용자 인터페이스(또는 둘 다)에서 대화형 역할을 수행하는지 여부를 나타내는 메서드를 구현합니다. 기본적으로 두 메서드 모두 `true`를 반환합니다. 이러한 설정에서는 화면 읽기 프로그램과 같은 자동화 도구의 유용성이 향상되며, 이러한 메서드를 사용하여 자동화 트리를 필터링할 수 있습니다. <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 메서드가 패턴 처리를 하위 요소 피어로 전송하는 경우 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 하위 요소 피어의 메서드는 false를 반환하여 하위 요소 피어를 자동화 트리에서 숨길 수 있습니다. 예를 들어 에서 <xref:System.Windows.Controls.ListBox> 스크롤은 <xref:System.Windows.Controls.ScrollViewer>에서 를 처리하고 에 <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> 대한 자동화 <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> 피어는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>에 연결된 메서드에 의해 반환됩니다. 따라서 반환 <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> 하는 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 메서드는 `false`자동화 <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> 트리에 나타나지 않도록 합니다.  
  
 자동화 피어는 컨트롤에 적절한 기본값을 제공해야 합니다. 컨트롤을 참조하는 XAML은 특성을 포함하여 <xref:System.Windows.Automation.AutomationProperties> 핵심 메서드의 피어 구현을 재정의할 수 있습니다. 예를 들어 다음 XAML에서는 사용자 지정된 두 가지 [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] 속성이 있는 단추를 만듭니다.  
  
```xaml  
<Button AutomationProperties.Name="Special"
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>패턴 공급자 구현  
 사용자 지정 공급자에 의해 구현 된 인터페이스는 소유 요소에서 <xref:System.Windows.Controls.Control>직접 파생 하는 경우 명시적으로 선언 됩니다. 예를 들어 다음 코드는 범위 값을 <xref:System.Windows.Controls.Control> 구현하는 a에 대한 피어를 선언합니다.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 소유 컨트롤이 와 같은 <xref:System.Windows.Controls.Primitives.RangeBase>특정 유형의 컨트롤에서 파생되는 경우 피어는 동등한 파생 피어 클래스에서 파생될 수 있습니다. 이 경우 피어는 <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer> <xref:System.Windows.Automation.Provider.IRangeValueProvider>의 기본 구현을 제공하는 에서 파생됩니다. 다음 코드에서는 이러한 피어의 선언을 보여 줍니다.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
구현의 경우 NumericUpDown 사용자 지정 컨트롤을 구현하고 사용하는 [C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) 또는 [Visual Basic](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) 소스 코드를 참조하십시오.  
  
### <a name="raise-events"></a>이벤트 발생  
 자동화 클라이언트는 자동화 이벤트를 구독할 수 있습니다. 사용자 지정 컨트롤은 <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> 메서드를 호출하여 컨트롤 상태에 대한 변경 내용을 보고해야 합니다. 마찬가지로 속성 값이 변경되면 메서드를 호출합니다. <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> 다음 코드에서는 컨트롤 코드 내에서 피어 개체를 가져오고 메서드를 호출하여 이벤트를 발생시키는 방법을 보여 줍니다. 최적화 방법으로 코드는 이 이벤트 유형에 대한 수신기가 있는지 확인합니다. 수신기가 있는 경우에만 이벤트가 발생되면 불필요한 오버헤드를 방지하고 컨트롤이 응답 가능한 상태를 유지하는 데 도움이 됩니다.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>참고 항목

- [UI 자동화 개요](../../ui-automation/ui-automation-overview.md)
- [서버 쪽 UI 자동화 공급자 구현](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [GitHub의 숫자업다운 사용자 지정 제어(C#)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [GitHub에서 숫자업다운 사용자 지정 컨트롤(시각적 기본)](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
