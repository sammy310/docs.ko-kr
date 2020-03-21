---
title: WPF 및 윈도우 폼 인터옵
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 76d1e97c92946267aa1217f52c93594fb63d20de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187157"
---
# <a name="wpf-and-windows-forms-interoperation"></a>WPF 및 Windows Forms 상호 운용성
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]및 Windows Forms는 응용 프로그램 인터페이스를 만들기 위한 두 가지 아키텍처를 제공합니다. 네임스페이스는 <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> 일반적인 상호 운용 시나리오를 활성화하는 클래스를 제공합니다. 상호 운용성 기능을 구현 하는 두 가지 주요 클래스는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 고 <xref:System.Windows.Forms.Integration.ElementHost>입니다. 이 항목에서는 지원되는 상호 운용성 시나리오와 지원되지 않는 시나리오를 설명합니다.  
  
> [!NOTE]
> *하이브리드 컨트롤* 시나리오에는 특별 고려 사항이 제공됩니다. 하이브리드 컨트롤에서는 한 기술의 컨트롤이 다른 기술의 컨트롤에 중첩되어 있습니다. 이 특징은 *중첩된 상호 운용성*이라고도 합니다. *다단계 하이브리드 컨트롤*에는 두 개 이상의 하이브리드 컨트롤 중첩 수준이 있습니다. 다중 중첩 상호 운용의 예로는 다른 Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms 컨트롤을 포함하는 컨트롤이 포함된 Windows Forms 컨트롤이 있습니다. 다단계 하이브리드 컨트롤은 지원되지 않습니다.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>WPF에서 Windows Forms 컨트롤 호스팅  
 다음 상호 운용 시나리오는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 Windows Forms 컨트롤을 호스트할 때 지원됩니다.  
  
- 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML을 사용하여 하나 이상의 Windows Forms 컨트롤을 호스트할 수 있습니다.  
  
- 코드를 사용하여 하나 이상의 Windows Forms 컨트롤을 호스트할 수 있습니다.  
  
- 다른 Windows Forms 컨트롤을 포함 하는 Windows Forms 컨테이너 컨트롤을 호스트할 수 있습니다.  
  
- 마스터 및 Windows Forms 세부 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 정보가 있는 마스터/세부 정보 양식을 호스트할 수 있습니다.  
  
- Windows Forms 마스터 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부 정보가 있는 마스터/세부 정보 양식을 호스트할 수 있습니다.  
  
- 하나 이상의 ActiveX 컨트롤을 호스트할 수 있습니다.  
  
- 하나 이상의 복합 컨트롤을 호스팅할 수 있습니다.  
  
- [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 하이브리드 컨트롤을 호스팅할 수 있습니다.  
  
- 코드를 사용하여 하이브리드 컨트롤을 호스팅할 수 있습니다.  
  
### <a name="layout-support"></a>레이아웃 지원  
 다음 목록에서는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 호스팅되는 Windows Forms 컨트롤을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 시스템에 통합하려고 할 때 알려진 제한 사항에 대해 설명합니다.  
  
- 경우에 따라 Windows Forms 컨트롤의 크기를 조정하거나 특정 차원에만 크기를 조정할 수 있습니다. 예를 들어 Windows <xref:System.Windows.Forms.ComboBox> Forms 컨트롤은 컨트롤의 글꼴 크기에 의해 정의되는 단일 높이만 지원합니다. 요소가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세로로 늘어갈 수 있다고 가정하는 동적 <xref:System.Windows.Forms.ComboBox> 레이아웃에서는 호스트된 컨트롤이 예상대로 늘어나지 않습니다.  
  
- Windows 양식 컨트롤은 회전하거나 비뚤어질 수 없습니다. 예를 들어 사용자 인터페이스를 90도로 회전하면 호스팅된 Windows Forms 컨트롤이 직립 위치를 유지합니다.  
  
- 대부분의 경우 Windows Forms 컨트롤은 비례 크기 조정을 지원하지 않습니다. 컨트롤의 전체 크기는 조정할 수 있지만, 컨트롤의 구성 요소와 자식 컨트롤의 크기가 예상대로 조정되지 않을 수 있습니다. 이러한 제한은 각 Windows Forms 컨트롤이 확장을 얼마나 잘 지원하는지에 따라 달라집니다.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 겹치는 동작을 제어하기 위해 요소의 z 순서를 변경할 수 있습니다. 호스팅된 Windows Forms 컨트롤은 별도의 HWND로 그려지므로 항상 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에 그려집니다.  
  
- Windows Forms 컨트롤은 글꼴 크기에 따라 자동 크기 조정을 지원합니다. 개별 요소의 크기는 동적으로 조정할 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용자 인터페이스에서 글꼴 크기를 변경해도 전체 레이아웃의 크기는 조정되지 않습니다.  
  
### <a name="ambient-properties"></a>앰비언트 속성  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 주변 속성 중 일부에는 Windows Forms 등가물입니다. 이러한 주변 속성은 호스트된 Windows Forms 컨트롤에 전파되고 컨트롤의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 공용 속성으로 노출됩니다. 컨트롤은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 각 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 주변 속성을 Windows Forms와 동등한 것으로 변환합니다.  
  
 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
### <a name="behavior"></a>동작  
 다음 테이블에서는 상호 운용성 동작을 설명합니다.  
  
|동작|지원됨|지원되지 않음|  
|--------------|---------------|-------------------|  
|투명성|Windows 양식 컨트롤 렌더링은 투명도를 지원합니다. 부모 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 배경은 호스팅된 Windows Forms 컨트롤의 배경이 될 수 있습니다.|일부 Windows 양식 컨트롤은 투명도를 지원하지 않습니다. 예를 들어 <xref:System.Windows.Forms.TextBox> 및 <xref:System.Windows.Forms.ComboBox> 컨트롤은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 호스팅할 때 투명하지 않습니다.|  
|탭 이동|호스팅된 Windows Forms 컨트롤의 탭 순서는 해당 컨트롤이 Windows Forms 기반 응용 프로그램에서 호스팅되는 경우와 동일합니다.<br /><br /> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] TAB 키와 SHIFT+TAB 키가 있는 컨트롤에서 Windows Forms 컨트롤로 탭하는 것은 평소와 같이 작동합니다.<br /><br /> 속성 값이 있는 <xref:System.Windows.Forms.Control.TabStop%2A> Windows Forms `false` 컨트롤은 사용자가 컨트롤을 통해 탭할 때 포커스를 받지 않습니다.<br /><br /> - <xref:System.Windows.Forms.Integration.WindowsFormsHost> 각 컨트롤에는 해당 <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤이 포커스를 수신할 시기를 결정하는 값이 있습니다.<br />- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨테이너 내에 포함된 Windows Forms 컨트롤은 속성에서 지정한 순서를 <xref:System.Windows.Forms.Control.TabIndex%2A> 따릅니다. 마지막 탭 인덱스에서 탭 이동하면 다음 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤(있는 경우)에 포커스를 둡니다. 다른 포커스 가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 있는 컨트롤이 없는 경우 탭 순서대로 첫 번째 Windows Forms 컨트롤로 돌아갑니다.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>는 컨트롤 에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 포함된 형제 Windows Forms 컨트롤을 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 기준으로 합니다.<br />-   탭 이동은 컨트롤별 동작을 준수합니다. 예를 들어 <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> 속성 값이 있는 컨트롤에서 TAB 키를 누르면 포커스를 이동하는 대신 텍스트 상자에 탭이 `true` 입력됩니다.|해당 사항 없음|  
|화살표 키를 사용하여 탐색|- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤의 화살표 키를 가진 탐색은 일반 Windows Forms 컨테이너 컨트롤과 동일합니다 : UP 화살표 및 왼쪽 화살표 키는 이전 컨트롤을 선택하고 아래쪽 화살표 및 오른쪽 화살표 키는 다음 컨트롤을 선택합니다.<br />- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함된 첫 번째 컨트롤의 위쪽 화살표 및 왼쪽 화살표 키는 SHIFT+TAB 키보드 단축키와 동일한 작업을 수행합니다. 포커스가 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 포커스가 컨트롤 외부로 이동합니다. 이 동작은 마지막 <xref:System.Windows.Forms.ContainerControl> 컨트롤에 대한 래핑이 발생하지 않는다는 점에서 표준 동작과 다릅니다. 다른 포커스 제어가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 없는 경우 포커스가 탭 순서대로 마지막 Windows Forms 컨트롤로 돌아갑니다.<br />- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함된 마지막 컨트롤의 아래쪽 화살표 및 오른쪽 화살표 키는 TAB 키와 동일한 작업을 수행합니다. 포커스가 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있는 경우 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 포커스가 컨트롤 외부로 이동합니다. 이 동작은 첫 <xref:System.Windows.Forms.ContainerControl> 번째 컨트롤에 대한 래핑이 발생하지 않는다는 점에서 표준 동작과 다릅니다. 다른 포커스 제어가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 없는 경우 포커스가 탭 순서의 첫 번째 Windows Forms 컨트롤로 돌아갑니다.|해당 사항 없음|  
|액셀러레이터|“지원되지 않음” 열에 명시된 경우를 제외하고는 액셀러레이터가 정상적으로 작동합니다.|기술 전체에서 중복된 액셀러레이터는 일반 중복 액셀러레이터처럼 작동하지 않습니다. 가속기가 기술 간에 중복되고 Windows Forms 컨트롤에 하나 이상 있고 다른 하나는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 복제되는 경우 Windows Forms 컨트롤은 항상 가속기를 받습니다. 중복 액셀러레이터를 누르면 컨트롤 간에 포커스가 전환되지 않습니다.|  
|바로 가기 키|“지원되지 않음” 열에 명시된 경우를 제외하고는 바로 가기 키가 정상적으로 작동합니다.|- 전처리 단계에서 처리되는 Windows Forms 바로 가기 키는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 항상 바로 가기 키보다 우선합니다. 예를 들어 CTRL+S 바로 가기 키가 정의된 <xref:System.Windows.Forms.ToolStrip> 컨트롤이 있고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] CTRL+S에 바인딩된 <xref:System.Windows.Forms.ToolStrip> 명령이 있는 경우 컨트롤 처리기는 포커스에 관계없이 항상 먼저 호출됩니다.<br />- <xref:System.Windows.Forms.Control.KeyDown> Windows Forms 바로 가기 키에서 마지막으로 처리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]됩니다. Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드를 재정의하거나 이벤트를 처리하여 <xref:System.Windows.Forms.Control.PreviewKeyDown> 이 동작을 방지할 수 있습니다. <xref:System.Windows.Forms.Control.IsInputKey%2A> 메서드에서 반환하거나 `true` 속성 값을 이벤트 <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> 처리기의 값으로 `true` 설정합니다. <xref:System.Windows.Forms.Control.PreviewKeyDown>|  
|AcceptsReturn, AcceptsTab 및 기타 컨트롤별 동작|기본 키보드 동작을 변경하는 속성은 Windows Forms 컨트롤이 반환할 <xref:System.Windows.Forms.Control.IsInputKey%2A> `true`메서드를 재정의한다고 가정하여 평소와 같이 작동합니다.|<xref:System.Windows.Forms.Control.KeyDown> 이벤트를 처리하여 기본 키보드 동작을 변경하는 Windows Forms 컨트롤은 호스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 마지막으로 처리됩니다. 이러한 컨트롤은 마지막으로 처리되므로 예기치 않은 동작이 발생할 수 있습니다.|  
|시작 및 종료 이벤트|포커스가 포함된 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤로 이동하지 않는 경우 단일 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에서 포커스가 변경될 때 입력 및 Leave 이벤트가 평소와 같이 발생합니다.|다음 포커스 변경이 발생하면 시작 및 종료 이벤트는 발생하지 않습니다.<br /><br /> - 내부에서 외부로 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤.<br />- 외부에서 컨트롤 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 내부로.<br />- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 외부.<br />- 컨트롤에서 호스팅되는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> Windows Forms <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 동일한 <xref:System.Windows.Forms.Integration.WindowsFormsHost>내부에서 호스팅되는 컨트롤까지.|  
|다중 스레딩|모든 종류의 다중 스레딩이 지원됩니다.|Windows Forms와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술 모두 단일 스레드 동시성 모델을 가정합니다. 디버깅 중에 다른 스레드에서 프레임워크 개체를 호출하면 이 요구 사항을 적용하기 위해 예외가 발생합니다.|  
|보안|모든 상호 운용성 시나리오에는 완전 신뢰가 필요합니다.|부분 신뢰에서는 상호 운용성 시나리오가 허용되지 않습니다.|  
|접근성|모든 접근성 시나리오가 지원됩니다. 보조 기술 제품은 Windows Forms 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 모두 포함하는 하이브리드 응용 프로그램에 사용될 때 올바르게 작동합니다.|해당 사항 없음|  
|클립보드|모든 클립보드 작업이 정상적으로 작동합니다. 여기에는 Windows 양식과 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 간의 절단 및 붙여넣기가 포함됩니다.|해당 사항 없음|  
|끌어서 놓기 기능|끌어서 놓기 작업이 모두 정상적으로 작동합니다. 여기에는 Windows 양식과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 간의 작업이 포함됩니다.|해당 사항 없음|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>Windows Forms에서 WPF 컨트롤 호스팅  
 Windows Forms 컨트롤이 컨트롤을 호스트할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다음 상호 운용 시나리오가 지원됩니다.  
  
- 코드를 사용하여 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 호스팅.  
  
- 속성 시트를 호스팅된 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤과 연결.  
  
- 양식에서 하나 이상의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지 호스팅.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창 시작.  
  
- Windows 양식 마스터 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부 정보로 마스터/세부 정보 양식을 호스팅합니다.  
  
- 마스터 및 Windows Forms [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 세부 정보가 있는 마스터/세부 정보 양식을 호스팅합니다.  
  
- 사용자 지정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 호스팅.  
  
- 하이브리드 컨트롤 호스팅.  
  
### <a name="ambient-properties"></a>앰비언트 속성  
 Windows Forms 컨트롤의 일부 주변 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성에는 등가속성이 있습니다. 이러한 주변 속성은 호스트된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에 전파되고 컨트롤의 <xref:System.Windows.Forms.Integration.ElementHost> 공용 속성으로 노출됩니다. 컨트롤은 <xref:System.Windows.Forms.Integration.ElementHost> 각 Windows Forms 주변 속성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 해당 속성으로 변환합니다.  
  
 자세한 내용은 [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)을 참조하세요.  
  
### <a name="behavior"></a>동작  
 다음 테이블에서는 상호 운용성 동작을 설명합니다.  
  
|동작|지원됨|지원되지 않음|  
|--------------|---------------|-------------------|  
|투명성|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 렌더링에서는 투명도를 지원합니다. 상위 Windows Forms 컨트롤의 배경이 호스트된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 배경이 될 수 있습니다.|해당 사항 없음|  
|다중 스레딩|모든 종류의 다중 스레딩이 지원됩니다.|Windows Forms와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기술 모두 단일 스레드 동시성 모델을 가정합니다. 디버깅 중에 다른 스레드에서 프레임워크 개체를 호출하면 이 요구 사항을 적용하기 위해 예외가 발생합니다.|  
|보안|모든 상호 운용성 시나리오에는 완전 신뢰가 필요합니다.|부분 신뢰에서는 상호 운용성 시나리오가 허용되지 않습니다.|  
|접근성|모든 접근성 시나리오가 지원됩니다. 보조 기술 제품은 Windows Forms 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤을 모두 포함하는 하이브리드 응용 프로그램에 사용될 때 올바르게 작동합니다.|해당 사항 없음|  
|클립보드|모든 클립보드 작업이 정상적으로 작동합니다. 여기에는 Windows 양식과 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 간의 절단 및 붙여넣기가 포함됩니다.|해당 사항 없음|  
|끌어서 놓기 기능|끌어서 놓기 작업이 모두 정상적으로 작동합니다. 여기에는 Windows 양식과 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 간의 작업이 포함됩니다.|해당 사항 없음|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Windows Forms 및 WPF 속성 매핑](windows-forms-and-wpf-property-mapping.md)
