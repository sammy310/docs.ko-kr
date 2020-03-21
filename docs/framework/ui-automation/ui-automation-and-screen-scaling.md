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
ms.openlocfilehash: 2a68a74fa6aadcaba21f142d394a1f8a3d8af371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179972"
---
# <a name="ui-automation-and-screen-scaling"></a>UI 자동화 및 화면 크기 조정
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
Windows Vista를 시작으로 Windows를 사용하면 화면의 대부분의 사용자 인터페이스(UI) 요소가 더 크게 표시되도록 인치당 점(dpi) 설정을 변경할 수 있습니다. 이 기능은 Windows에서 오랫동안 사용할 수 있었지만 이전 버전에서는 응용 프로그램에서 확장프로그램을 구현해야 했습니다. Windows Vista부터 시작하여 데스크톱 창 관리자는 자체 크기 조정을 처리하지 않는 모든 응용 프로그램에 대해 기본 크기 조정을 수행합니다. UI 자동화 클라이언트 애플리케이션에서는 이 기능을 고려해야 합니다.  
  
<a name="Scaling_in_Windows_Vista"></a>
## <a name="scaling-in-windows-vista"></a>Windows Vista에서 크기 조정  
 기본 dpi 설정은 96이며, 이는 96픽셀이 1개의 명목 인치의 너비 또는 높이를 차지한다는 것을 의미합니다. "인치"의 정확한 측정값은 모니터의 크기와 실제 해상도에 따라 달라집니다. 예를 들어, 12인치 너비의 모니터에서 1280픽셀의 수평 해상도의 경우 96픽셀의 가로줄은 1인치의 약 9/10입니다.  
  
 dpi 설정을 변경하는 것은 화면 해상도를 변경하는 것과 다다. dpi 배율을 사용하면 화면의 실제 픽셀 수가 동일하게 유지됩니다. 하지만 크기 조정은 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 요소의 크기와 위치에 적용됩니다. 크기를 조정하지 말라는 메시지가 명시적으로 표시되지 않는 데스크톱 및 애플리케이션에 대해서는 바탕 화면 창 관리자가 이 크기 조정을 자동으로 수행할 수 있습니다.  
  
 실제로 사용자가 배율 계수를 120dpi로 설정하면 화면의 수직 또는 수평 인치가 25% 커집니다. 그에 따라 모든 치수가 적절하게 조정됩니다. 화면 위쪽에서 왼쪽 가장자리까지 애플리케이션 창의 오프셋이 25% 늘어납니다. 응용 프로그램 크기 조정을 사용하도록 설정하고 응용 프로그램이 dpi 를 인식하지 못하는 경우 창의 크기는 포함된 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 모든 요소의 오프셋 및 크기와 함께 동일한 비율로 증가합니다.  
  
> [!NOTE]
> 기본적으로 DWM은 사용자가 dpi를 120으로 설정할 때 dpi 인식되지 않는 응용 프로그램에 대한 크기 조정을 수행하지 않지만 dpi가 사용자 지정 값 144 이상으로 설정될 때 수행합니다. 그러나 사용자는 기본 동작을 재정의할 수 있습니다.  
  
 화면 크기 조정 어떤 방식으로든 화면 좌표와 관련된 애플리케이션에 대한 새로운 문제를 만듭니다. 이제 화면에는 물리적 좌표와 논리적 좌표 두 개가 포함됩니다. 점의 물리적 좌표는 원점의 왼쪽 상단에서의 픽셀 단위의 실제 오프셋입니다. 논리적 좌표는 픽셀 자체의 크기가 조정된 경우 발생되는 오프셋입니다.  
  
 좌표 (100, 48)에서 단추가 있는 대화 상자를 설계한다고 가정해 보세요. 이 대화 상자가 기본 96dpi에 표시되면 단추는 물리적 좌표(100, 48)에 있습니다. 120 dpi에서 물리적 좌표(125, 60)에 위치합니다. 그러나 논리 좌표는 모든 dpi 설정에서 동일합니다: (100, 48).  
  
 논리 좌표는 dpi 설정에 관계없이 운영 체제 및 응용 프로그램의 동작을 일관되게 만들기 때문에 중요합니다. 예를 들어, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> 은 일반적으로 논리적 좌표를 반환합니다. 대화 상자의 요소 위로 커서를 이동하면 dpi 설정에 관계없이 동일한 좌표가 반환됩니다. 컨트롤을 (100, 100)에서 그리면 해당 논리 좌표에 그려지고 모든 dpi 설정에서 동일한 상대 위치를 차지합니다.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>
## <a name="scaling-in-ui-automation-clients"></a>UI 자동화 클라이언트의 크기 조정  
 API는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 논리 좌표를 사용하지 않습니다. 다음 메서드 및 속성은 물리적 좌표를 반환하거나 매개 변수로 간주합니다.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 기본적으로 96dpi가 아닌 환경에서 실행되는 UI 자동화 클라이언트 응용 프로그램은 이러한 메서드 및 속성에서 올바른 결과를 얻을 수 없습니다. 예를 들어, 커서 위치는 논리적 좌표에 있기 때문에 클라이언트가 이러한 좌표를 <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> 에 간단히 전달하여 커서 아래에 있는 요소를 가져올 수 없습니다. 또한 애플리케이션이 클라이언트 영역 외부에 창을 올바르게 배치할 수 없습니다.  
  
 솔루션은 두 부분으로 구성됩니다.  
  
1. 먼저 클라이언트 응용 프로그램 dpi를 인식합니다. 이렇게 하려면 시작 시 Win32 함수를 `SetProcessDPIAware` 호출합니다. 관리 코드에서, 다음 선언을 통해 이 함수를 사용할 수 있습니다.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     이 함수는 전체 프로세스dpi를 인식하게 하므로 프로세스에 속한 모든 창의 크기가 조정되지 않습니다. 예를 들어 [하이라이터 샘플에서](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)강조 표시 사각형을 구성하는 네 개의 창은 논리적 좌표가 아닌 UI 자동화에서 얻은 물리적 좌표에 있습니다. 샘플이 dpi 를 인식하지 못하면 바탕 화면의 논리적 좌표에 강조 표시가 그려지므로 96-dpi가 아닌 환경에서 잘못된 배치가 발생합니다.  
  
2. 커서 좌표를 얻으려면 Win32 함수를 `GetPhysicalCursorPos`호출합니다. 다음 예제에서는 이 함수를 선언하고 사용하는 방법을 보여 줍니다.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>는 사용하지 마세요. 크기가 조정된 환경에서 클라이언트 창 외부에서의 이 속성 동작이 정의되지 않았습니다.  
  
 응용 프로그램이 비dpi 인식 응용 프로그램과 직접 프로세스 간 통신을 수행하는 경우 Win32 함수 `PhysicalToLogicalPoint` 및 `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>참고 항목

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
