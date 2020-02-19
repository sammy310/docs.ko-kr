---
title: '방법: Win32 호스트 컨테이너를 사용하여 적중 테스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: a86c1c36f75fa232d52731959371268a8b2593d7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452807"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>방법: Win32 호스트 컨테이너를 사용하여 적중 테스트
시각적 개체에 대 한 호스트 창 컨테이너를 제공 하 여 Win32 창 내에서 시각적 개체를 만들 수 있습니다. 포함된 시각적 개체에 대한 이벤트 처리를 제공하려면 호스트 창 컨테이너의 메시지 필터 루프에 전달된 메시지를 처리합니다. Win32 창에서 시각적 개체를 호스트 하는 방법에 대 한 자세한 내용은 [자습서: Win32 응용 프로그램에서 시각적 개체 호스팅](tutorial-hosting-visual-objects-in-a-win32-application.md) 을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 시각적 개체의 호스트 컨테이너로 사용 되는 Win32 창에 대해 마우스 이벤트 처리기를 설정 하는 방법을 보여 줍니다.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 다음 예제에서는 특정 마우스 이벤트 트래핑에 대 한 응답으로 적중 테스트를 설정 하는 방법을 보여 줍니다.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource> 개체는 Win32 창에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 콘텐츠를 표시 합니다. <xref:System.Windows.Interop.HwndSource> 개체의 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성 값은 시각적 트리 계층 구조의 최상위 노드를 나타냅니다.  
  
 Win32 호스트 컨테이너를 사용 하 여 적중 테스트 개체에 대 한 전체 샘플을 보려면 [Win32 상호 운용성을 사용한 적중 테스트 샘플](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Interop.HwndSource>
- [시각적 계층에서 적중 테스트](hit-testing-in-the-visual-layer.md)
- [자습서: Win32 애플리케이션에서 시각적 개체 호스팅](tutorial-hosting-visual-objects-in-a-win32-application.md)
