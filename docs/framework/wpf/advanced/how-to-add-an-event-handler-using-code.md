---
title: '방법: 코드를 사용하여 이벤트 처리기 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- event handlers [WPF], adding
- XAML [WPF], adding event handlers
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
ms.openlocfilehash: 10f8e0899e61d5d54589c910bdcbcd92d8ee947c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777067"
---
# <a name="how-to-add-an-event-handler-using-code"></a>방법: 코드를 사용하여 이벤트 처리기 추가
이 예제에서는 코드를 사용 하 여 요소에 이벤트 처리기를 추가 하는 방법을 보여 줍니다.  
  
 이벤트 처리기를 추가 하려는 경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소와 요소를 포함 하는 태그 페이지 이미 로드 된 코드를 사용 하 여 처리기를 추가 해야 합니다. 또는 코드를 사용 하 여 전체 및 사용 하 여 모든 요소를 선언 하지 않으면 응용 프로그램에 대 한 요소 트리를 작성 하는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 생성 된 요소 트리에 이벤트 처리기를 추가 하는 특정 메서드를 호출할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 <xref:System.Windows.Controls.Button> 처음에 정의 된 기존 페이지에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]입니다. 코드 숨김 파일을 이벤트 처리기 메서드를 구현 하 고 다음에 새 이벤트 처리기로 해당 메서드를 추가 합니다 <xref:System.Windows.Controls.Button>합니다.  
  
 C# 사용 하 여 예제를 `+=` 이벤트 처리기를 할당 하는 연산자입니다. 처리기를 할당 하는 데 사용 되는 동일한 연산자는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 처리 모델입니다. Microsoft Visual Basic의 이벤트 처리기를 추가 하는 것이 연산자를 지원 하지 않습니다. 대신 두 가지 기술 중 하나가 필요합니다.  
  
- 사용 하 여 합니다 <xref:System.Windows.UIElement.AddHandler%2A> 메서드를 함께 `AddressOf` 연산자, 이벤트 처리기 구현을 참조 합니다.  
  
- 사용 된 `Handles` 이벤트 처리기 정의의 일부로 키워드입니다. 이 기술은 여기서는 표시 되지 않습니다. 참조 [Visual Basic 및 WPF 이벤트 처리](visual-basic-and-wpf-event-handling.md)합니다.  
  
 [!code-xaml[RoutedEventAddRemoveHandler#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  에 처음으로 구문 분석 된 이벤트 처리기를 추가 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지는 훨씬 더 간단 합니다. 이벤트 처리기를 추가 하려는 개체 요소 내에서 처리 하려는 이벤트의 이름과 일치 하는 특성을 추가 합니다. 다음의 코드 숨김 파일에 정의 된 이벤트 처리기 메서드의 이름으로 해당 특성의 값을 지정 합니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지입니다. 자세한 내용은 [XAML 개요 (WPF)](xaml-overview-wpf.md) 하거나 [라우트된 이벤트 개요](routed-events-overview.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [라우트된 이벤트 개요](routed-events-overview.md)
- [방법 항목](events-how-to-topics.md)
