---
title: UI 자동화 및 화면 크기 조정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: ceab7db1f9eeb47ec020e220ec702af8181855e2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442486"
---
# <a name="ui-automation-and-screen-scaling"></a>UI 자동화 및 화면 크기 조정
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
Starting with Windows Vista, Windows enables users to change the dots per inch (dpi) setting so that most user interface (UI) elements on the screen appear larger. Although this feature has long been available in Windows, in previous versions the scaling had to be implemented by applications. Starting with Windows Vista, the Desktop Window Manager performs default scaling for all applications that do not handle their own scaling. UI 자동화 클라이언트 애플리케이션에서는 이 기능을 고려해야 합니다.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Windows Vista에서 크기 조정  
 The default dpi setting is 96, which means that 96 pixels occupy a width or height of one notional inch. "인치"의 정확한 측정값은 모니터의 크기와 실제 해상도에 따라 달라집니다. 예를 들어, 12인치 너비의 모니터에서 1280픽셀의 수평 해상도의 경우 96픽셀의 가로줄은 1인치의 약 9/10입니다.  
  
 Changing the dpi setting is not the same as changing the screen resolution. With dpi scaling, the number of physical pixels on the screen remains the same. 하지만 크기 조정은 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소의 크기와 위치에 적용됩니다. 크기를 조정하지 말라는 메시지가 명시적으로 표시되지 않는 데스크톱 및 애플리케이션에 대해서는 바탕 화면 창 관리자가 이 크기 조정을 자동으로 수행할 수 있습니다.  
  
 In effect, when the user sets the scale factor to 120 dpi, a vertical or horizontal inch on the screen becomes bigger by 25 percent. 그에 따라 모든 치수가 적절하게 조정됩니다. 화면 위쪽에서 왼쪽 가장자리까지 애플리케이션 창의 오프셋이 25% 늘어납니다. If application scaling is enabled and the application is not dpi-aware, the size of the window increases in the same proportion, along with the offsets and sizes of all [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elements it contains.  
  
> [!NOTE]
> By default, the DWM does not perform scaling for non-dpi-aware applications when the user sets the dpi to 120, but does perform it when the dpi is set to a custom value of 144 or higher. 그러나 사용자는 기본 동작을 재정의할 수 있습니다.  
  
 화면 크기 조정 어떤 방식으로든 화면 좌표와 관련된 애플리케이션에 대한 새로운 문제를 만듭니다. 이제 화면에는 물리적 좌표와 논리적 좌표 두 개가 포함됩니다. 점의 물리적 좌표는 원점의 왼쪽 상단에서의 픽셀 단위의 실제 오프셋입니다. 논리적 좌표는 픽셀 자체의 크기가 조정된 경우 발생되는 오프셋입니다.  
  
 좌표 (100, 48)에서 단추가 있는 대화 상자를 설계한다고 가정해 보세요. When this dialog box is displayed at the default 96 dpi, the button is located at physical coordinates of (100, 48). At 120 dpi, it is located at physical coordinates of (125, 60). But the logical coordinates are the same at any dpi setting: (100, 48).  
  
 Logical coordinates are important, because they make the behavior of the operating system and applications consistent regardless of the dpi setting. 예를 들어, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> 은 일반적으로 논리적 좌표를 반환합니다. If you move the cursor over an element in a dialog box, the same coordinates are returned regardless of the dpi setting. If you draw a control at (100, 100), it is drawn to those logical coordinates, and will occupy the same relative position at any dpi setting.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>UI 자동화 클라이언트의 크기 조정  
 The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API does not use logical coordinates. 다음 메서드 및 속성은 물리적 좌표를 반환하거나 매개 변수로 간주합니다.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 By default, a UI Automation client application running in a non-96- dpi environment will not be able to obtain correct results from these methods and properties. 예를 들어, 커서 위치는 논리적 좌표에 있기 때문에 클라이언트가 이러한 좌표를 <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> 에 간단히 전달하여 커서 아래에 있는 요소를 가져올 수 없습니다. 또한 애플리케이션이 클라이언트 영역 외부에 창을 올바르게 배치할 수 없습니다.  
  
 솔루션은 두 부분으로 구성됩니다.  
  
1. First, make the client application dpi-aware. 이렇게 하려면 시작 시에 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 함수 `SetProcessDPIAware` 를 호출합니다. 관리 코드에서, 다음 선언을 통해 이 함수를 사용할 수 있습니다.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     This function makes the entire process dpi-aware, meaning that all windows that belong to the process are unscaled. In the [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), for instance, the four windows that make up the highlight rectangle are located at the physical coordinates obtained from UI Automation, not the logical coordinates. If the sample were not dpi-aware, the highlight would be drawn at the logical coordinates on the desktop, which would result in incorrect placement in a non-96- dpi environment.  
  
2. 커서 좌표를 가져오려면 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 함수 `GetPhysicalCursorPos`를 호출합니다. 다음 예제에서는 이 함수를 선언하고 사용하는 방법을 보여 줍니다.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>는 사용하지 마세요. 크기가 조정된 환경에서 클라이언트 창 외부에서의 이 속성 동작이 정의되지 않았습니다.  
  
 If your application performs direct cross-process communication with non- dpi-aware applications, you may have convert between logical and physical coordinates by using the [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] functions `PhysicalToLogicalPoint` and `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>참조

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
