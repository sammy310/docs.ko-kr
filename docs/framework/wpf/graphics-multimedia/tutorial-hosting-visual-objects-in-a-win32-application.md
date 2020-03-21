---
title: '자습서: Win32 애플리케이션에서 시각적 개체 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: d04357e0770bbf8eebe8f40a86a19ddc9baae3ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187423"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>자습서: Win32 애플리케이션에서 시각적 개체 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 애플리케이션을 만들기 위한 다양한 환경을 제공합니다. 그러나 Win32 코드에 상당한 투자를 하는 경우 코드를 다시 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 작성하는 대신 응용 프로그램에 기능을 추가하는 것이 더 효과적일 수 있습니다. 응용 프로그램에서 동시에 사용되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32 및 그래픽 하위 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시스템에 대한 지원을 제공하려면 Win32 창에서 개체를 호스팅하는 메커니즘을 제공합니다.  
  
 이 자습서에서는 Win32 창에서 시각적 개체를 호스트하는 샘플 응용 프로그램인 [Hit Test와 Win32 상호 운용 샘플을](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)작성하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 방법을 설명합니다.  

<a name="requirements"></a>
## <a name="requirements"></a>요구 사항  
 이 자습서는 Win32 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍모두에 대한 기본적인 친숙함을 가정합니다. 프로그래밍에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 대한 기본 소개는 [연습: 내 첫 번째 WPF 데스크톱 응용 프로그램을](../getting-started/walkthrough-my-first-wpf-desktop-application.md)참조하십시오. Win32 프로그래밍에 대한 소개는 주제에 대한 수많은 책, 특히 찰스 페츨의 *프로그래밍 윈도우를* 참조하십시오.  
  
> [!NOTE]
> 이 자습서에는 관련 샘플의 많은 코드 예제가 포함되어 있습니다. 그러나 가독성을 위해 전체 샘플 코드를 포함하지는 않습니다. 전체 샘플 코드는 [Win32 상호 운용 샘플을 사용하여 적중 테스트를](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)참조하십시오.  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a>호스트 Win32 창 만들기  
 Win32 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창에서 개체를 호스팅하는 <xref:System.Windows.Interop.HwndSource> 열쇠는 클래스입니다. 이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Win32 창에서 개체를 래핑하여 하위 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 창으로 통합할 수 있도록 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Interop.HwndSource> 개체를 시각적 개체에 대 한 Win32 컨테이너 창으로 만드는 코드를 보여 주다. Win32 창의 창 스타일, 위치 및 기타 매개 변수를 설정하려면 개체를 <xref:System.Windows.Interop.HwndSourceParameters> 사용합니다.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> 속성의 값은 WS_EX_TRANSPARENT 설정할 수 없습니다. 즉, 호스트 Win32 창이 투명할 수 없습니다. 이러한 이유로 호스트 Win32 창의 배경 색은 상위 창과 동일한 배경 색으로 설정됩니다.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a>호스트 Win32 창에 시각적 개체 추가  
 시각적 개체에 대한 호스트 Win32 컨테이너 창을 만든 후에는 시각적 개체를 추가할 수 있습니다. 애니메이션과 같은 시각적 개체의 변환이 호스트 Win32 창의 경계 사각형의 경계를 초과하지 않도록 해야 합니다.  
  
 다음 예제에서는 개체를 만들고 <xref:System.Windows.Interop.HwndSource> 개체개체를 추가하기 위한 코드를 보여 주며, 개체에 추가합니다.  
  
> [!NOTE]
> <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성은 호스트 Win32 창에 추가 된 첫 번째 시각적 개체로 설정 됩니다. 루트 시각적 개체는 시각적 개체 트리의 최상위 노드를 정의합니다. 호스트 Win32 창에 추가된 모든 후속 시각적 개체는 자식 개체로 추가됩니다.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a>Win32 메시지 필터 구현  
 시각적 개체에 대한 호스트 Win32 창에는 응용 프로그램 큐에서 창으로 전송되는 메시지를 처리하는 창 메시지 필터 프로시저가 필요합니다. 창 프로시저는 Win32 시스템에서 메시지를 수신합니다. 이러한 메시지를 입력 메시지이거나 창 관리 메시지일 수 있습니다. 필요에 따라 창 절차에서 메시지를 처리하거나 기본 처리를 위해 메시지를 시스템으로 전달할 수 있습니다.  
  
 시각적 <xref:System.Windows.Interop.HwndSource> 개체의 부모로 정의한 개체는 제공한 창 메시지 필터 프로시저를 참조해야 합니다. 개체를 <xref:System.Windows.Interop.HwndSource> 만들 때 창 <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> 프로시저를 참조하도록 속성을 설정합니다.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 다음 예제에서는 왼쪽 및 오른쪽 마우스 단추 잠금 메시지를 처리하기 위한 코드를 보여 줍니다. 마우스 적중 위치의 좌표값은 `lParam` 매개변수 값에 포함되어 있습니다.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a>Win32 메시지 처리  
 다음 예제의 코드는 호스트 Win32 창에 포함된 시각적 개체의 계층 구조에 대해 적중 테스트가 수행되는 방법을 보여 주며 있습니다. 메서드를 사용하여 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 루트 시각적 개체와 적중할 좌표 값을 지정하여 점이 시각적 개체의 형상 내에 있는지 여부를 식별할 수 있습니다. 이 경우 루트 시각적 개체는 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성 <xref:System.Windows.Interop.HwndSource> 값입니다.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 시각적 개체에 대한 적중 테스트에 대한 자세한 내용은 [시각적 계층의 적중 테스트](hit-testing-in-the-visual-layer.md)를 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Interop.HwndSource>
- [Win32 상호 운용성을 사용하는 적중 테스트 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [시각적 계층에서 적중 테스트](hit-testing-in-the-visual-layer.md)
