---
title: '방법: 시각적 개체의 그리기 콘텐츠 열거'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930078"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="5fc9b-102">방법: 시각적 개체의 그리기 콘텐츠 열거</span><span class="sxs-lookup"><span data-stu-id="5fc9b-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="5fc9b-103">개체 <xref:System.Windows.Media.Drawing> 는<xref:System.Windows.Media.Visual>의 콘텐츠를 열거 하기 위한 개체 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc9b-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fc9b-104">예제</span><span class="sxs-lookup"><span data-stu-id="5fc9b-104">Example</span></span>  
 <span data-ttu-id="5fc9b-105">다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 메서드를 사용 하 여의 <xref:System.Windows.Media.DrawingGroup> <xref:System.Windows.Media.Visual> 값을 검색 하 고이를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fc9b-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fc9b-106">시각적 개체의 콘텐츠를 열거 하는 경우 개체를 검색 <xref:System.Windows.Media.Drawing> 하 고 렌더링 데이터의 기본 표현이 벡터 그래픽 명령 목록으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fc9b-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="5fc9b-107">자세한 내용은 [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5fc9b-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="5fc9b-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fc9b-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="5fc9b-109">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="5fc9b-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="5fc9b-110">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="5fc9b-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
