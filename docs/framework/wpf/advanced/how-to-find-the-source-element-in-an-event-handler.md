---
title: '방법: 이벤트 처리기에서 소스 요소 찾기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 8c1ff53e5af1ddfda17328291c5e22b57a8fe0e2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359469"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="4078e-102">방법: 이벤트 처리기에서 소스 요소 찾기</span><span class="sxs-lookup"><span data-stu-id="4078e-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="4078e-103">이 예제에서는 이벤트 처리기에서 소스 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4078e-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4078e-104">예제</span><span class="sxs-lookup"><span data-stu-id="4078e-104">Example</span></span>  
 <span data-ttu-id="4078e-105">다음 예제는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 코드 숨김 파일에 선언 된 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="4078e-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="4078e-106">사용자가 처리기에 연결 된 단추를 클릭 하면 처리기 속성 값을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4078e-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="4078e-107">처리기 코드를 사용 하는 <xref:System.Windows.RoutedEventArgs.Source%2A> 속성 변경 이벤트 인수에서 보고 되는 라우트된 이벤트 데이터의는 <xref:System.Windows.FrameworkElement.Width%2A> 속성 값에는 <xref:System.Windows.RoutedEventArgs.Source%2A> 요소.</span><span class="sxs-lookup"><span data-stu-id="4078e-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="4078e-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="4078e-108">See also</span></span>
- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="4078e-109">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="4078e-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="4078e-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="4078e-110">How-to Topics</span></span>](events-how-to-topics.md)
