---
title: Windows Forms 및 WPF interop 입력 아키텍처
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
ms.openlocfilehash: f79971ba13691ccc36420e39696b7b8a46e5ce0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745056"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Windows Forms 및 WPF 상호 운용성 입력 아키텍처
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 간의 상호 운용을 위해서는 두 기술 모두 적절 한 키보드 입력을 처리 해야 합니다. 이 항목에서는 이러한 기술이 키보드 및 메시지 처리를 구현 하 여 하이브리드 응용 프로그램의 원활한 상호 운용을 가능 하 게 하는 방법을 설명 합니다.  
  
 이 항목에는 다음과 같은 하위 단원이 포함되어 있습니다.  
  
- 모덜리스 폼 및 대화 상자  
  
- WindowsFormsHost 키보드 및 메시지 처리  
  
- ElementHost 키보드 및 메시지 처리  
  
## <a name="modeless-forms-and-dialog-boxes"></a>모덜리스 폼 및 대화 상자  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소에 대 한 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> 메서드를 호출 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에서 모덜리스 폼 이나 대화 상자를 엽니다.  
  
 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> 메서드를 호출 하 여 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]기반 응용 프로그램에서 모덜리스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지를 엽니다.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost 키보드 및 메시지 처리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 프로그램에서 호스트 되는 경우 키보드 및 메시지 처리는 다음과 같이 구성 됩니다.  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 <xref:System.Windows.Interop.ComponentDispatcher> 클래스에서 구현 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프에서 메시지를 가져옵니다.  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 일반적인 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 키보드 처리가 발생 하도록 서로게이트 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프를 만듭니다.  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]로 포커스 관리를 조정 하기 위해 <xref:System.Windows.Interop.IKeyboardInputSink> 인터페이스를 구현 합니다.  
  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤 자체를 등록 하 고 메시지 루프를 시작 합니다.  
  
 다음 섹션에서는 이러한 프로세스 부분에 대해 자세히 설명 합니다.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>WPF 메시지 루프에서 메시지 가져오기  
 <xref:System.Windows.Interop.ComponentDispatcher> 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]메시지 루프 관리자를 구현 합니다. <xref:System.Windows.Interop.ComponentDispatcher> 클래스는 외부 클라이언트가 메시지를 필터링 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 처리 하기 전에 메시지를 필터링 할 수 있도록 후크를 제공 합니다.  
  
 상호 운용 구현은 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트를 처리 합니다 .이 이벤트를 사용 하면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 이전에 메시지를 처리할 수 있습니다.  
  
### <a name="surrogate-windows-forms-message-loop"></a>서로게이트 Windows Forms 메시지 루프  
 기본적으로 <xref:System.Windows.Forms.Application?displayProperty=nameWithType> 클래스에는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램에 대 한 기본 메시지 루프가 포함 되어 있습니다. 상호 운용 하는 동안 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 메시지 루프는 메시지를 처리 하지 않습니다. 따라서이 논리를 재현 해야 합니다. <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트에 대 한 처리기는 다음 단계를 수행 합니다.  
  
1. <xref:System.Windows.Forms.IMessageFilter> 인터페이스를 사용 하 여 메시지를 필터링 합니다.  
  
2. <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> 메서드를 호출합니다.  
  
3. 필요한 경우 메시지를 변환 하 고 디스패치합니다.  
  
4. 메시지를 처리 하는 다른 컨트롤이 없으면 메시지를 호스팅 컨트롤에 전달 합니다.  
  
### <a name="ikeyboardinputsink-implementation"></a>System.windows.interop.ikeyboardinputsink> 구현  
 서로게이트 메시지 루프는 키보드 관리를 처리 합니다. 따라서 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 메서드는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 클래스에서 구현 해야 하는 유일한 <xref:System.Windows.Interop.IKeyboardInputSink> 멤버입니다.  
  
 기본적으로 <xref:System.Windows.Interop.HwndHost> 클래스는 <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 구현에 대 한 `false`을 반환 합니다. 이렇게 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤로의 탭 이동이 방지 됩니다.  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> 메서드의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 구현은 다음 단계를 수행 합니다.  
  
1. <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 포함 되어 있으며 포커스를 받을 수 있는 첫 번째 또는 마지막 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 찾습니다. 제어 선택은 트래버스 정보에 따라 달라 집니다.  
  
2. 포커스를 컨트롤에 설정 하 고 `true`을 반환 합니다.  
  
3. 포커스를 받을 수 있는 컨트롤이 없으면 `false`반환 합니다.  
  
### <a name="windowsformshost-registration"></a>WindowsFormsHost 등록  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤에 대 한 창 핸들이 만들어지면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 메시지 루프의 현재 상태를 등록 하는 내부 정적 메서드를 호출 합니다.  
  
 등록 하는 동안 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤은 메시지 루프를 검사 합니다. 메시지 루프를 시작 하지 않은 경우 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트 처리기가 만들어집니다. 메시지 루프는 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> 이벤트 처리기가 연결 될 때 실행 중인 것으로 간주 됩니다.  
  
 창 핸들이 소멸 되 면 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤이 등록에서 자신을 제거 합니다.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>ElementHost 키보드 및 메시지 처리  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그램에서 호스트 되는 경우 키보드 및 메시지 처리는 다음과 같이 구성 됩니다.  
  
- <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스 구현을 구현 합니다.  
  
- 탭 이동 및 화살표 키.  
  
- 명령 키와 대화 상자 키  
  
- 가속기 처리를 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 합니다.  
  
 다음 섹션에서는 이러한 부분에 대해 자세히 설명 합니다.  
  
### <a name="interface-implementations"></a>인터페이스 구현  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]키보드 메시지는 포커스가 있는 컨트롤의 창 핸들로 라우팅됩니다. <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 이러한 메시지는 호스팅된 요소로 라우팅됩니다. 이를 위해 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤은 <xref:System.Windows.Interop.HwndSource> 인스턴스를 제공 합니다. <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에 포커스가 있는 경우 <xref:System.Windows.Interop.HwndSource> 인스턴스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 클래스에서 처리 될 수 있도록 대부분의 키보드 입력을 라우팅합니다.  
  
 <xref:System.Windows.Interop.HwndSource> 클래스는 <xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스를 구현 합니다.  
  
 키보드 상호 운용성은 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 메서드를 구현 하 여 호스팅된 요소 밖으로 포커스를 이동 하는 TAB 키와 화살표 키 입력을 처리 합니다.  
  
### <a name="tabbing-and-arrow-keys"></a>탭 이동 및 화살표 키  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 선택 논리는 TAB 키와 화살표 키 탐색을 구현 하는 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> 및 <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> 메서드에 매핑됩니다. <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> 메서드를 재정의 하면이 매핑이 수행 됩니다.  
  
### <a name="command-keys-and-dialog-box-keys"></a>명령 키 및 대화 상자 키  
 명령 키와 대화 상자 키를 처리 하는 첫 번째 기회 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제공 하기 위해 명령 전처리 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 메서드에 연결 됩니다. <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> 메서드를 재정의 하면 두 가지 기술이 연결 됩니다.  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> 메서드를 사용 하면 호스팅된 요소가 TAB, ENTER, ESC 및 화살표 키와 같은 명령 키를 비롯 하 여 WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN 또는 WM_SYSKEYUP 같은 키 메시지를 처리할 수 있습니다. 키 메시지가 처리 되지 않으면 처리를 위해 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 상위 계층으로 전송 됩니다.  
  
### <a name="accelerator-processing"></a>가속기 처리  
 액셀러레이터를 올바르게 처리 하려면 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 액셀러레이터 처리를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> 클래스에 연결 해야 합니다. 또한 모든 WM_CHAR 메시지는 호스트 된 요소로 올바르게 라우트 되어야 합니다.  
  
 <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> 메서드의 기본 <xref:System.Windows.Interop.HwndSource> 구현은 `false`을 반환 하기 때문에 WM_CHAR 메시지는 다음 논리를 사용 하 여 처리 됩니다.  
  
- <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> 메서드는 모든 WM_CHAR 메시지가 호스팅된 요소로 전달 되도록 하기 위해 재정의 됩니다.  
  
- ALT 키를 누르면 메시지가 WM_SYSCHAR 됩니다. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]은 <xref:System.Windows.Forms.Control.IsInputChar%2A> 메서드를 통해이 메시지를 전처리 하지 않습니다. 따라서 <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> 메서드는 등록 된 액셀러레이터에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager>를 쿼리하도록 재정의 됩니다. 등록 된 액셀러레이터 키가 발견 되 면 <xref:System.Windows.Input.AccessKeyManager> 처리 합니다.  
  
- ALT 키를 누르지 않으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> 클래스가 처리 되지 않은 입력을 처리 합니다. 입력이 액셀러레이터 인 경우 <xref:System.Windows.Input.AccessKeyManager> 처리 합니다. <xref:System.Windows.Input.InputManager.PostProcessInput> 이벤트는 처리 되지 않은 WM_CHAR 메시지에 대해 처리 됩니다.  
  
 사용자가 ALT 키를 누르면 액셀러레이터 키 표시 신호가 전체 폼에 표시 됩니다. 이 동작을 지원 하기 위해 포커스가 있는 컨트롤에 관계 없이 활성 폼의 모든 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 WM_SYSKEYDOWN 메시지를 받습니다.  
  
 메시지는 활성 폼의 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에만 전송 됩니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [연습: WPF에서 Windows Forms 복합 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
