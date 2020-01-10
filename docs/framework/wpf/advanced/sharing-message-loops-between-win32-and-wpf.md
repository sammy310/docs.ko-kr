---
title: Win32와 WPF 간에 메시지 루프 공유
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 5c1d75ab9598196e9cffc78a2f116993e722fd38
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740322"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Win32와 WPF 간에 메시지 루프 공유
이 항목에서는 <xref:System.Windows.Threading.Dispatcher>의 기존 메시지 루프 노출을 사용 하거나 상호 운용 코드의 Win32 쪽에서 별도의 메시지 루프를 만들어 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]와의 상호 운용을 위한 메시지 루프를 구현 하는 방법에 대해 설명 합니다.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher 및 메시지 루프  
 상호 운용성 및 키보드 이벤트 지원에 대 한 일반적인 시나리오는 <xref:System.Windows.Interop.IKeyboardInputSink>를 구현 하거나 이미 <xref:System.Windows.Interop.IKeyboardInputSink>를 구현 하는 클래스 (예: <xref:System.Windows.Interop.HwndSource> 또는 <xref:System.Windows.Interop.HwndHost>)에서 서브 클래스를 구현 하는 것입니다. 그러나 키보드 싱크 지원에서는 상호 운용 경계를 넘어 메시지를 보내고 받을 때 발생할 수 있는 모든 메시지 루프 요구를 해결 하지는 않습니다. 응용 프로그램 메시지 루프 아키텍처를 공식화 하는 데 도움이 되도록 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 메시지 루프에서 수행할 단순 프로토콜을 정의 하는 <xref:System.Windows.Interop.ComponentDispatcher> 클래스를 제공 합니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>는 여러 멤버를 노출 하는 정적 클래스입니다. 각 메서드의 범위는 암시적으로 호출 스레드에 연결 됩니다. 메시지 루프는 다음 섹션에 정의 된 대로 중요 한 시간에 이러한 Api 중 일부를 호출 해야 합니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>는 다른 구성 요소 (예: 키보드 싱크)가 수신할 수 있는 이벤트를 제공 합니다. <xref:System.Windows.Threading.Dispatcher> 클래스는 적절 한 시퀀스에서 적절 한 <xref:System.Windows.Interop.ComponentDispatcher> 메서드를 모두 호출 합니다. 사용자 고유의 메시지 루프를 구현 하는 경우 코드는 비슷한 방식으로 <xref:System.Windows.Interop.ComponentDispatcher> 메서드를 호출 하는 일을 담당 합니다.  
  
 스레드에서 <xref:System.Windows.Interop.ComponentDispatcher> 메서드를 호출 하면 해당 스레드에 등록 된 이벤트 처리기만 호출 됩니다.  
  
## <a name="writing-message-loops"></a>메시지 루프 작성  
 다음은 고유한 메시지 루프를 작성 하는 경우 사용 하는 <xref:System.Windows.Interop.ComponentDispatcher> 멤버에 대 한 검사 목록입니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: 메시지 루프가이를 호출 하 여 스레드가 모달 임을 나타내야 합니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: 메시지 루프에서이를 호출 하 여 스레드가 모달이 아닌 상태로 되돌아간 것을 나타내야 합니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: 메시지 루프에서이를 호출 하 여 <xref:System.Windows.Interop.ComponentDispatcher>에서 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 이벤트를 발생 시켜야 함을 나타내야 합니다. <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> `true`경우에는 <xref:System.Windows.Interop.ComponentDispatcher> <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 발생 하지 않지만 모달 상태에서 <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>에 응답할 수 없는 경우에도 메시지 루프에서 <xref:System.Windows.Interop.ComponentDispatcher>를 호출 하도록 선택할 수 있습니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: 메시지 루프에서이를 호출 하 여 새 메시지를 사용할 수 있음을 나타내야 합니다. 반환 값은 <xref:System.Windows.Interop.ComponentDispatcher> 이벤트에 대 한 수신기가 메시지를 처리 했는지 여부를 나타냅니다. <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>에서 `true` (처리 됨)를 반환 하는 경우 디스패처는 메시지를 사용 하 여 아무런 작업도 수행 하지 않아야 합니다. 반환 값이 `false`이면 디스패처가 `TranslateMessage`Win32 함수를 호출한 다음 `DispatchMessage`를 호출 해야 합니다.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>ComponentDispatcher 및 기존 메시지 처리 사용  
 다음은 고유 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 루프를 사용 하는 경우 사용 하는 <xref:System.Windows.Interop.ComponentDispatcher> 멤버에 대 한 검사 목록입니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: 응용 프로그램에 모달이 있는지 여부를 반환 합니다 (예: 모달 메시지 루프가 푸시되 었는 지). 클래스가 메시지 루프의 <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> 및 <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> 호출 수를 유지 관리 하기 때문에 <xref:System.Windows.Interop.ComponentDispatcher>이 상태를 추적할 수 있습니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 및 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 이벤트는 대리자 호출에 대 한 표준 규칙을 따릅니다. 대리자는 지정 되지 않은 순서로 호출 되며, 첫 번째 대리자가 메시지를 처리 된 것으로 표시 한 경우에도 모든 대리자가 호출 됩니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: 유휴 처리를 수행 하는 데 적절 하 고 효율적인 시간을 나타냅니다 (스레드에 대해 보류 중인 다른 메시지가 없음). 스레드가 모달이 면 <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> 발생 하지 않습니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: 메시지 펌프가 처리 하는 모든 메시지에 대해 발생 합니다.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>중에 처리 되지 않은 모든 메시지에 대해 발생 합니다.  
  
 <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> 이벤트 나 <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 이벤트가 발생 한 후 이벤트 데이터에서 참조로 전달 되는 `handled` 매개 변수가 `true`경우 메시지가 처리 된 것으로 간주 됩니다. `handled` `true`되는 경우 이벤트 처리기는 메시지를 무시 해야 합니다. 즉, 다른 처리기가 메시지를 먼저 처리 했기 때문입니다. 두 이벤트 모두에 대 한 이벤트 처리기에서 메시지를 수정할 수 있습니다. 디스패처는 변경 되지 않은 원래 메시지를 전달 하는 것이 아니라 수정 된 메시지를 디스패치합니다. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>은 모든 수신기로 전달 되지만 아키텍처는 대상 메시지가 메시지에 응답 하 여 코드를 호출 해야 하는 HWND를 포함 하는 최상위 창만 있습니다.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>System.windows.interop.hwndsource>에서 ComponentDispatcher 이벤트를 처리 하는 방법  
 <xref:System.Windows.Interop.HwndSource> 최상위 창인 경우 (부모 HWND가 없는 경우) <xref:System.Windows.Interop.ComponentDispatcher>에 등록 됩니다. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> 발생 하 고 메시지가 <xref:System.Windows.Interop.HwndSource> 또는 자식 창에 대해 만들어진 경우 <xref:System.Windows.Interop.HwndSource>는 <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> 키보드 싱크 시퀀스를 호출 합니다.  
  
 <xref:System.Windows.Interop.HwndSource> 최상위 창이 아닌 경우 (부모 HWND가 있는 경우) 처리 되지 않습니다. 최상위 창만 처리를 수행 하 고, 상호 운용 시나리오의 일부로 키보드 싱크를 지 원하는 최상위 창이 될 것으로 예상 됩니다.  
  
 적절 한 키보드 싱크 메서드를 먼저 호출 하지 않고 <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndHost.WndProc%2A>를 호출 하면 응용 프로그램에서 <xref:System.Windows.UIElement.KeyDown>같은 더 높은 수준의 키보드 이벤트를 받게 됩니다. 그러나 액세스 키 지원과 같은 바람직한 키보드 입력 모델 기능을 우회 하는 키보드 싱크 메서드는 호출 되지 않습니다. 이 문제는 메시지 루프가 <xref:System.Windows.Interop.ComponentDispatcher>에서 관련 스레드를 제대로 알리거나 부모 HWND가 적절 한 키보드 싱크 응답을 호출 하지 않았기 때문에 발생할 수 있습니다.  
  
 <xref:System.Windows.Interop.HwndSource.AddHook%2A> 메서드를 사용 하 여 해당 메시지에 대 한 후크를 추가한 경우 키보드 싱크로 이동 하는 메시지를 HWND로 보낼 수 없습니다. 메시지가 메시지 펌프 수준에서 직접 처리 되 고 `DispatchMessage` 함수에 전송 되지 않았을 수 있습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
- [스레딩 모델](threading-model.md)
- [입력 개요](input-overview.md)
