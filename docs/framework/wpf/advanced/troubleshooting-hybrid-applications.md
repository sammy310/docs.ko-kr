---
title: 혼합 애플리케이션 문제 해결
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: b85a607d2e44d6253359a81118f90e6ee05d2d3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187322"
---
# <a name="troubleshooting-hybrid-applications"></a>혼합 애플리케이션 문제 해결
<a name="introduction"></a>이 항목에서는 두 가지 모두 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 Windows Forms 기술을 사용하는 하이브리드 응용 프로그램을 작성할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열합니다.  

<a name="overlapping_controls"></a>
## <a name="overlapping-controls"></a>컨트롤 겹침  
 컨트롤이 예상대로 겹치지 않을 수 있습니다. Windows 양식은 각 컨트롤에 대해 별도의 HWND를 사용합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 페이지의 모든 콘텐츠에 대해 하나의 HWND를 사용합니다. 이러한 구현 차이로 인해 예기치 않은 겹치는 동작이 발생합니다.  
  
 호스팅되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Forms 컨트롤은 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 위에 나타납니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]컨트롤에서 호스팅되는 <xref:System.Windows.Forms.Integration.ElementHost> 콘텐츠는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 z 순서로 나타납니다. 컨트롤을 겹칠 <xref:System.Windows.Forms.Integration.ElementHost> 수 있지만 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠는 결합하거나 상호 작용하지 않습니다.  
  
<a name="child_property"></a>
## <a name="child-property"></a>자식 속성  
 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> 클래스는 단일 자식 컨트롤 또는 요소만 호스트할 수 있습니다. 둘 이상의 컨트롤이나 요소를 호스트하려면 컨테이너를 자식 콘텐츠로 사용해야 합니다. 예를 들어 Windows Forms 단추를 추가하고 확인란 <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> 컨트롤을 컨트롤에 추가한 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 다음 패널을 컨트롤의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 속성에 할당할 수 있습니다. 그러나 단추를 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 추가 하 고 동일한 컨트롤에 별도로 확인 란 컨트롤을 추가할 수 없습니다.  
  
<a name="scaling"></a>
## <a name="scaling"></a>확장  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]및 Windows 양식에는 다른 크기 조정 모델이 있습니다. 일부 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 크기 조정 변환은 Windows Forms 컨트롤에 의미가 있지만 다른 변환은 그렇지 않습니다. 예를 들어 Windows Forms 컨트롤의 크기 조정을 0으로 조정하는 것이 작동하지만 동일한 컨트롤을 0이 아닌 값으로 다시 확장하려고 하면 컨트롤의 크기는 0으로 유지됩니다. 자세한 내용은 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](layout-considerations-for-the-windowsformshost-element.md)을 참조하세요.  
  
<a name="adapter"></a>
## <a name="adapter"></a>어댑터  
 숨겨진 컨테이너를 포함하기 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> 때문에 클래스및 작업 할 때 혼동이있을 수 있습니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스와 <xref:System.Windows.Forms.Integration.ElementHost> 클래스에는 콘텐츠를 호스트하는 데 사용하는 *어댑터라는*숨겨진 컨테이너가 있습니다. 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 경우 어댑터는 <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> 클래스에서 파생됩니다. 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost> 경우 어댑터는 <xref:System.Windows.Controls.DockPanel> 요소에서 파생됩니다. 다른 상호 운용성 항목에 어댑터에 대한 참조가 표시되는 경우 이 컨테이너에 대해 설명하는 것입니다.  
  
<a name="nesting"></a>
## <a name="nesting"></a>중첩  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 내부에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 중첩하는 것은 지원되지 않습니다. 요소 내부에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 중첩하는 것도 지원되지 않습니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
  
<a name="focus"></a>
## <a name="focus"></a>Focus  
 포커스는 하이브리드 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 포커스 문제가 발생할 수 있음을 의미하는 Windows Forms와에서 다르게 작동합니다. 예를 들어 요소 내부에 포커스가 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 있고 페이지를 최소화 및 복원하거나 모달 대화 상자를 표시하는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 경우 요소 내부의 초점이 손실될 수 있습니다. 요소에는 여전히 포커스가 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 있지만 내부의 컨트롤은 그렇지 않을 수 있습니다.  
  
 데이터 유효성 검사도 포커스의 영향을 받습니다. 유효성 검사는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 작동하지만 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에서 탭하거나 두 개의 서로 다른 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 간에 탭할 때 작동하지 않습니다.  
  
<a name="property_mapping"></a>
## <a name="property-mapping"></a>속성 매핑  
 일부 속성 매핑에서는 Windows Forms 기술과 Windows Forms [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술 간의 서로 다른 구현을 브리지하기 위해 광범위한 해석이 필요합니다. 속성 매핑을 사용하면 코드가 글꼴, 색 및 기타 속성의 변경에 반응하도록 할 수 있습니다. 일반적으로 속성 매핑은 *Property*Changed 이벤트나 On*Property*Changed 호출을 수신 대기하고 자식 컨트롤이나 해당 어댑터에서 적절한 속성을 설정하여 작동합니다. 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
<a name="layoutrelated_properties_on_hosted_content"></a>
## <a name="layout-related-properties-on-hosted-content"></a>호스트된 콘텐츠의 레이아웃 관련 속성  
 또는 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> 속성이 할당되면 호스팅된 콘텐츠의 여러 레이아웃 관련 속성이 자동으로 설정됩니다. 이러한 콘텐츠 속성을 변경하면 예기치 않은 레이아웃 동작이 발생할 수 있습니다.  
  
 호스팅된 콘텐츠가 도킹되어 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> 상위 콘텐츠와 상위 콘텐츠를 채웁니다. 이 채우기 동작을 사용하려면 자식 속성을 설정할 때 여러 가지 속성을 설정합니다. 다음 표에는 <xref:System.Windows.Forms.Integration.ElementHost> 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스에 의해 설정된 콘텐츠 속성이 나열됩니다.  
  
|호스트 클래스|콘텐츠 속성|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 호스트된 콘텐츠에서 직접 이러한 속성을 설정하지 마세요. 자세한 내용은 [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](layout-considerations-for-the-windowsformshost-element.md)을 참조하세요.  
  
<a name="navigation_applications"></a>
## <a name="navigation-applications"></a>탐색 애플리케이션  
 탐색 애플리케이션에서 사용자 상태를 유지하지 않을 수 있습니다. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 탐색 응용 프로그램에서 사용할 때 해당 컨트롤을 다시 만듭니다. 자식 컨트롤을 다시 만드는 것은 사용자가 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 호스팅하는 페이지에서 멀리 이동한 다음 다시 돌아올 때 발생합니다. 사용자가 입력한 모든 콘텐츠가 손실됩니다.  
  
<a name="message_loop_interoperation"></a>
## <a name="message-loop-interoperation"></a>메시지 루프 상호 운용성  
 Windows Forms 메시지 루프로 작업할 때 메시지가 예상대로 처리되지 않을 수 있습니다. 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 생성자에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호출합니다. 이 메서드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프에 메시지 필터를 추가합니다. 이 필터는 <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> a가 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 메시지의 대상인 경우 메서드를 호출하고 메시지를 번역/디스패치합니다.  
  
 을 사용하여 <xref:System.Windows.Window> <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>Windows Forms 메시지 루프에 a를 표시하는 경우 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 메서드를 호출하지 않으면 아무 것도 입력할 수 없습니다. 메서드는 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> <xref:System.Windows.Window> <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>을 사용하여 키워드 관련 메시지를 메시지 루프에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다시 라우팅하는 를 추가합니다. 자세한 내용은 [Windows Forms 및 WPF 상호 운용성 입력 아키텍처](windows-forms-and-wpf-interoperability-input-architecture.md)를 참조하세요.  
  
<a name="opacity_and_layering"></a>
## <a name="opacity-and-layering"></a>불투명도 및 레이어  
 클래스는 <xref:System.Windows.Interop.HwndHost> 계층화를 지원하지 않습니다. <xref:System.Windows.UIElement.Opacity%2A> 즉, <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 속성을 설정하면 효과가 없으며 로 설정된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다른 창에서는 혼합이 <xref:System.Windows.Window.AllowsTransparency%2A> `true`발생하지 않습니다.  
  
<a name="dispose"></a>
## <a name="dispose"></a>Dispose  
 클래스를 올바르게 삭제하지 않으면 리소스가 누출될 수 있습니다. 하이브리드 응용 프로그램에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 및 <xref:System.Windows.Forms.Integration.ElementHost> 클래스가 삭제되었는지 또는 리소스가 누출될 수 있는지 확인합니다. Windows Forms는 <xref:System.Windows.Forms.Integration.ElementHost> 모달이 <xref:System.Windows.Forms.Form> 아닌 부모가 닫히면 컨트롤을 삭제합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]응용 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 프로그램이 종료될 때 요소를 삭제합니다. Windows Forms 메시지 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Window> 루프에서 요소를 표시할 수 있습니다. 이 경우 코드에서 애플리케이션이 종료되고 있다는 알림을 받을 수 없습니다.  
  
<a name="enabling_visual_styles"></a>
## <a name="enabling-visual-styles"></a>비주얼 스타일 사용  
 Windows 양식 컨트롤의 Microsoft Windows XP 시각적 스타일이 활성화되지 않을 수 있습니다. 메서드는 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Windows Forms 응용 프로그램에 대 한 템플릿에서 호출 됩니다. 이 메서드는 기본적으로 호출 되지 않습니다 하지만 프로젝트를 만들 시각적 스튜디오를 사용 하는 경우 Comctl32.dll의 버전 6.0을 사용할 수 있는 경우 컨트롤에 대 한 Microsoft Windows XP 시각적 스타일을 가져옵니다. 핸들이 스레드에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 만들어지기 전에 메서드를 호출해야 합니다. 자세한 내용은 [방법: 혼합 애플리케이션에서 비주얼 스타일 사용](how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하세요.  
  
<a name="licensed_controls"></a>
## <a name="licensed-controls"></a>사용이 허가된 컨트롤  
 사용이 허가된 Windows Forms 컨트롤은 사용자에게 메시지 상자에 라이선스 정보를 표시하는 컨트롤로 하이브리드 응용 프로그램에 예기치 않은 동작이 발생할 수 있습니다. 일부 사용이 허가된 컨트롤은 핸들 만들기에 대한 응답으로 대화 상자를 표시합니다. 예를 들어 사용이 허가된 컨트롤은 라이선스가 필요하다거나 컨트롤의 평가판 사용이 세 개 남아 있음을 사용자에게 알릴 수 있습니다.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 <xref:System.Windows.Interop.HwndHost> 클래스에서 파생되고 자식 컨트롤의 핸들은 <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 메서드 내에서 만들어집니다. 클래스는 <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> 메서드에서 메시지를 처리할 수 없지만 대화 상자를 표시하면 메시지가 전송됩니다. 이 라이선스 시나리오를 사용하려면 <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> 컨트롤을 요소의 자식으로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 할당하기 전에 컨트롤의 메서드를 호출합니다.  
  
<a name="wpf_designer"></a>
## <a name="wpf-designer"></a>WPF Designer  
 비주얼 스튜디오용 WPF 디자이너를 사용하여 WPF 콘텐츠를 디자인할 수 있습니다. 다음 섹션에서는 WPF 디자이너를 사용하여 하이브리드 응용 프로그램을 작성할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열합니다.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent가 디자인 타임에 무시됨  
 디자인 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 타임에 속성이 예상대로 작동하지 않을 수 있습니다.  
  
 WPF 컨트롤이 표시되는 상위에 없는 경우 WPF 런타임은 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 값을 무시합니다. 무시될 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 수 있는 이유는 <xref:System.Windows.Forms.Integration.ElementHost> 개체가 별도의 <xref:System.AppDomain>로 만들어지기 때문입니다. 그러나 응용 프로그램을 실행 <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> 하면 예상 대로 작동 합니다.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>obj 폴더를 삭제하면 디자인 타임 오류 목록이 나타남  
 obj 폴더를 삭제하면 디자인 타임 오류 목록이 나타납니다.  
  
 을 사용하여 <xref:System.Windows.Forms.Integration.ElementHost>디자인할 때 Windows Forms 디자이너는 프로젝트의 obj 폴더 내의 디버그 또는 릴리스 폴더에서 생성된 파일을 사용합니다. 이러한 파일을 삭제하면 디자인 타임 오류 목록이 나타납니다. 이 문제를 해결하려면 프로젝트를 다시 빌드하세요. 자세한 내용은 [Windows Forms 디자이너의 디자인 타임 오류](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)를 참조하세요.  
  
<a name="elementhost_and_ime"></a>
## <a name="elementhost-and-ime"></a>ElementHost 및 IME  
 <xref:System.Windows.Forms.Integration.ElementHost> 현재 에서 호스팅되는 WPF 컨트롤은 <xref:System.Windows.Forms.Control.ImeMode%2A> 속성을 지원하지 않습니다. 에 <xref:System.Windows.Forms.Control.ImeMode%2A> 대한 변경 내용은 호스트된 컨트롤에서 무시됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [WPF Designer의 상호 운용성](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Windows Forms 및 WPF 상호 운용성 입력 아키텍처](windows-forms-and-wpf-interoperability-input-architecture.md)
- [방법: 혼합 애플리케이션에서 비주얼 스타일 사용](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [WindowsFormsHost 요소에 대한 레이아웃 고려 사항](layout-considerations-for-the-windowsformshost-element.md)
- [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)
- [Windows Forms 디자이너의 디자인 타임 오류](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [마이그레이션 및 상호 운용성](migration-and-interoperability.md)
