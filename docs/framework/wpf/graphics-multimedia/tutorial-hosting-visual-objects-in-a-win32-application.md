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
ms.openlocfilehash: b260f96246f0d9e5447b74a05e1396bfef176197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111464"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>자습서: Win32 애플리케이션에서 시각적 개체 호스팅
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 만들기 위한 풍부한 환경을 제공 합니다. 그러나 상당한 투자 경우 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 코드를이 더 효과적일 추가할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 기능을 코드를 다시 작성 하지 않고 있습니다. 에 대 한 지원을 제공 하기 위해 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 하위 시스템 응용 프로그램에서 동시에 사용할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체의 호스팅 메커니즘을 제공을 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창.  
  
 이 자습서에서는 샘플 응용 프로그램을 작성 하는 방법 설명 [Win32 상호 운용 샘플을 사용 하 여 적중 테스트](https://go.microsoft.com/fwlink/?LinkID=159995), 해당 호스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시각적 개체는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창입니다.  

<a name="requirements"></a>   
## <a name="requirements"></a>요구 사항  
 이 자습서에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그래밍에 대한 기본 지식이 있다고 가정합니다. 에 대 한 기본적인 소개 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그래밍 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다. 에 대 한 소개 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 주제에 참조를 특히 프로그래밍 서적 중 하나 *Windows 프로그래밍* Charles petzold가 저술한 합니다.  
  
> [!NOTE]
>  이 자습서에는 관련 샘플의 많은 코드 예제가 포함되어 있습니다. 그러나 가독성을 위해 전체 샘플 코드를 포함하지는 않습니다. 전체 샘플 코드를 보려면 [Win32 상호 운용 샘플을 사용 하 여 적중 테스트](https://go.microsoft.com/fwlink/?LinkID=159995)합니다.  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>호스트 Win32 창 만들기  
 호스팅하는 데 핵심적인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 기간은 <xref:System.Windows.Interop.HwndSource> 클래스입니다. 이 클래스가 래핑하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개체를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 통합할 수 있도록 프로그램 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 자식 창으로 합니다.  
  
 다음 예제에서는 만들기 위한 코드를 <xref:System.Windows.Interop.HwndSource> 개체는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시각적 개체에 대 한 컨테이너 창. 창 스타일, 위치 및 기타 매개 변수를 설정 하는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창을 사용 하 여는 <xref:System.Windows.Interop.HwndSourceParameters> 개체입니다.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  값을 <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> 속성 WS_EX_TRANSPARENT로 설정할 수 없습니다. 즉, 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창이 투명 할 수 없습니다. 이러한 이유로 호스트의 배경색 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창은 부모 창과 같은 배경색으로 설정 됩니다.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>호스트 Win32 창에 시각적 개체 추가  
 호스트를 만든 후 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨테이너 창 시각적 개체에 대 한 시각적 개체를 추가할 수 있습니다. 애니메이션과 같은 시각적 개체에 대 한 변환이 호스트의 경계를 벗어나 확장 하지 않는 확인 하려는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창의 경계 사각형입니다.  
  
 다음 예제에서는 만들기 위한 코드는 <xref:System.Windows.Interop.HwndSource> 개체 및 시각적 개체를 추가 합니다.  
  
> [!NOTE]
>  합니다 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 의 속성을 <xref:System.Windows.Interop.HwndSource> 개체가 호스트에 추가 하는 첫 번째 시각적 개체에 설정 된 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창입니다. 루트 시각적 개체는 시각적 개체 트리의 최상위 노드를 정의합니다. 호스트에 추가 된 모든 후속 visual 개체 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 자식 개체로 추가 됩니다.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Win32 메시지 필터 구현  
 호스트 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창에 시각적 개체에 대 한 응용 프로그램 큐에서 창으로 전송 되는 메시지를 처리 하는 창 메시지 필터 프로시저가 필요 합니다. 창 프로시저에서 메시지를 수신 합니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시스템입니다. 이러한 메시지를 입력 메시지이거나 창 관리 메시지일 수 있습니다. 필요에 따라 창 절차에서 메시지를 처리하거나 기본 처리를 위해 메시지를 시스템으로 전달할 수 있습니다.  
  
 <xref:System.Windows.Interop.HwndSource> 개체 사용자가 정의한 대로 시각적 개체에 대 한 부모 제공한 창 메시지 필터 절차를 참조 해야 합니다. 만들 때 합니다 <xref:System.Windows.Interop.HwndSource> 개체, 설정 된 <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> 창 프로시저를 참조 하는 속성.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 다음 예제에서는 왼쪽 및 오른쪽 마우스 단추 잠금 메시지를 처리하기 위한 코드를 보여 줍니다. 좌표 값은 마우스 클릭 위치의 값에 포함 된를 `lParam` 매개 변수입니다.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Win32 메시지 처리  
 다음 예제에서 코드는 호스트에 포함 된 시각적 개체의 계층 구조에 대해 적중된 테스트를 수행 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창입니다. 사용 하 여 점이 시각적 개체의 기 하 도형 내 여부를 확인할 수는 <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> 루트 시각적 개체 및 좌표 값에 대해 적중 테스트를 지정 하는 방법입니다. 이 경우 루트 시각적 개체의 값인 합니다 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 의 속성을 <xref:System.Windows.Interop.HwndSource> 개체.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 시각적 개체에 대해 적중 테스트에 대 한 자세한 내용은 참조 하세요. [시각적 계층에서 테스트 적중](hit-testing-in-the-visual-layer.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Interop.HwndSource>
- [적중 테스트 Win32 상호 운용성 샘플](https://go.microsoft.com/fwlink/?LinkID=159995)
- [시각적 계층에서 적중 테스트](hit-testing-in-the-visual-layer.md)
