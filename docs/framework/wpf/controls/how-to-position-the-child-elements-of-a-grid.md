---
title: '방법: Grid의 자식 요소 위치 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186716"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="1d2a6-102">방법: Grid의 자식 요소 위치 지정</span><span class="sxs-lookup"><span data-stu-id="1d2a6-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="1d2a6-103">이 예제에서는 자식 요소를 배치하기 위해 <xref:System.Windows.Controls.Grid> 정의된 get 및 set 메서드를 사용하는 방법을 보여 주어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d2a6-104">예제</span><span class="sxs-lookup"><span data-stu-id="1d2a6-104">Example</span></span>  
 <span data-ttu-id="1d2a6-105">다음 예제에서는 세 <xref:System.Windows.Controls.Grid> 개의`grid1`열과 세 개의 행이 있는 부모 요소()를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="1d2a6-106">자식 <xref:System.Windows.Shapes.Rectangle> 요소()는`rect1`열 <xref:System.Windows.Controls.Grid> 위치 0, 행 위치 0에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="1d2a6-107"><xref:System.Windows.Controls.Button>요소는 에서 요소를 재배치하기 위해 <xref:System.Windows.Shapes.Rectangle> 호출할 <xref:System.Windows.Controls.Grid>수 있는 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="1d2a6-108">사용자가 단추를 클릭하면 관련 메서드가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="1d2a6-109">다음 코드 숨결 예제는 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 발생시키는 메서드를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="1d2a6-110">이 예제는 관련 <xref:System.Windows.Controls.TextBlock> get 메서드를 사용하여 새 속성 값을 문자열로 출력하는 요소에 이러한 메서드 호출을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="1d2a6-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="1d2a6-111">완성 된 결과는 이쪽!</span><span class="sxs-lookup"><span data-stu-id="1d2a6-111">Here is the finished result!</span></span>

 ![스크린 샷은 두 개의 열WPF 사용자 인터페이스를 묘사하고, 오른쪽에는 3 x 3 그리드가 있고 왼쪽에는 그리드의 열과 행 사이에 컬러 사각형을 이동하는 버튼이 있습니다.](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="1d2a6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d2a6-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="1d2a6-114">패널 개요</span><span class="sxs-lookup"><span data-stu-id="1d2a6-114">Panels Overview</span></span>](panels-overview.md)
