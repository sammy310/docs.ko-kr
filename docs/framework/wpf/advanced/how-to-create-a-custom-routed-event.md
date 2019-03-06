---
title: '방법: 사용자 지정 라우트된 이벤트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: c351bec05fa8ad8438cb8521f6ab1e6277a40b1d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373402"
---
# <a name="how-to-create-a-custom-routed-event"></a>방법: 사용자 지정 라우트된 이벤트 만들기
이벤트 라우팅을 지원 하도록 사용자 지정 이벤트를 등록 해야는 <xref:System.Windows.RoutedEvent> 를 사용 하는 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 메서드. 이 예제에서는 사용자 지정 라우트된 이벤트를 만드는 데 대한 기본 사항을 설명합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서와 같이 처음 등록할를 <xref:System.Windows.RoutedEvent> 를 사용 하는 <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> 메서드. 규칙에 따라 합니다 <xref:System.Windows.RoutedEvent> 정적 필드 이름을 접미사로 끝나야 ***이벤트***합니다. 이 예제에서는 이벤트의 이름은 `Tap` 이벤트의 라우팅 전략 이며 <xref:System.Windows.RoutingStrategy.Bubble>합니다. 등록 호출 후에는 이벤트에 대한 추가 및 제거 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 접근자를 제공할 수 있습니다.  
  
 이 예제에서는 `OnTap`이라는 가상 메서드를 통해 이벤트를 발생시키지만 이벤트를 발생시키는 방법 및 이벤트가 변경에 응답하는 방법은 필요에 맞게 설정할 수 있습니다.  
  
 이 예제에서 기본적으로의 서브 클래스 전체를 구현 함을 또한 <xref:System.Windows.Controls.Button>; 해당 서브 클래스를 별도 어셈블리로 빌드한 이며를 별도의 사용자 지정 클래스로 인스턴스화합니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지입니다. 이는 다른 컨트롤로 구성된 트리에 서브클래싱된 컨트롤을 삽입할 수 있고, 이 경우 이러한 컨트롤의 사용자 지정 이벤트의 이벤트 라우팅 기능이 모든 네이티브 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 요소의 이벤트 라우팅 기능과 동일하다는 점을 보여 주기 위함입니다.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 터널링 이벤트를 하지만 사용 하 여 동일한 생성 됩니다 <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> 로 <xref:System.Windows.RoutingStrategy.Tunnel> 는 등록 호출 합니다. 규칙에 따라 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 터널링 이벤트에는 “Preview”라는 접두사가 붙습니다.  
  
 버블링 이벤트 작동 방식에 대한 예제를 보려면 [라우트된 이벤트 처리](how-to-handle-a-routed-event.md)를 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [라우트된 이벤트 개요](routed-events-overview.md)
- [입력 개요](input-overview.md)
- [컨트롤 제작 개요](../controls/control-authoring-overview.md)
