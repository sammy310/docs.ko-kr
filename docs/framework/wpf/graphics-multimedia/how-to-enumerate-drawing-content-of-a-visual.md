---
title: '방법: 시각적 개체의 그리기 콘텐츠 열거'
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 4f0afc1075fe66c7f154fcef3cd883709db55316
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108006"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="f0dd5-102">방법: 시각적 개체의 그리기 콘텐츠 열거</span><span class="sxs-lookup"><span data-stu-id="f0dd5-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="f0dd5-103">합니다 <xref:System.Windows.Media.Drawing> 의 콘텐츠를 열거 하는 것에 대 한 개체 모델을 제공 하는 개체는 <xref:System.Windows.Media.Visual>합니다.</span><span class="sxs-lookup"><span data-stu-id="f0dd5-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0dd5-104">예제</span><span class="sxs-lookup"><span data-stu-id="f0dd5-104">Example</span></span>  
 <span data-ttu-id="f0dd5-105">다음 예제에서는 <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> 검색 하는 메서드를 <xref:System.Windows.Media.DrawingGroup> 값을 <xref:System.Windows.Media.Visual> 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0dd5-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0dd5-106">검색 하려는 시각적 개체의 내용을 열거 하는 경우 <xref:System.Windows.Media.Drawing> 개체 및 없습니다 기본 표시는 렌더링 데이터의 벡터 그래픽 명령 목록으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0dd5-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="f0dd5-107">자세한 내용은 [WPF 그래픽 렌더링 개요](wpf-graphics-rendering-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0dd5-107">For more information, see [WPF Graphics Rendering Overview](wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="f0dd5-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0dd5-108">See also</span></span>

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="f0dd5-109">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="f0dd5-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="f0dd5-110">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="f0dd5-110">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
