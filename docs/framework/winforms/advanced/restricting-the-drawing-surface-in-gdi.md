---
title: GDI+에서 그리기 화면 제한
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, clipping
- clipping [Windows Forms], using GDI+
- GDI+, restricting drawing surface
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
ms.openlocfilehash: d0508166f905b45789ce638b03d0747dd6fa904e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074965"
---
# <a name="restricting-the-drawing-surface-in-gdi"></a><span data-ttu-id="b6aa4-102">GDI+에서 그리기 화면 제한</span><span class="sxs-lookup"><span data-stu-id="b6aa4-102">Restricting the Drawing Surface in GDI+</span></span>
<span data-ttu-id="b6aa4-103">클리핑은 특정 사각형 또는 영역에 그리기를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6aa4-103">Clipping involves restricting drawing to a certain rectangle or region.</span></span> <span data-ttu-id="b6aa4-104">다음 그림은 문자열 "Hello" 잘린 하트 모양의 영역을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6aa4-104">The following illustration shows the string "Hello" clipped to a heart-shaped region.</span></span>  
  
 <span data-ttu-id="b6aa4-105">![제한 된 그리기 화면](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span><span class="sxs-lookup"><span data-stu-id="b6aa4-105">![Restricted Drawing Surface](./media/aboutgdip02-art30.gif "AboutGdip02_Art30")</span></span>  
  
## <a name="clipping-with-regions"></a><span data-ttu-id="b6aa4-106">클리핑 영역</span><span class="sxs-lookup"><span data-stu-id="b6aa4-106">Clipping with Regions</span></span>  
 <span data-ttu-id="b6aa4-107">영역 경로에서 생성할 수 있습니다 및 클리핑에 대 한 윤곽선이 있는 텍스트를 사용할 수 있도록 경로 문자열의 윤곽선을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6aa4-107">Regions can be constructed from paths, and paths can contain the outlines of strings, so you can use outlined text for clipping.</span></span> <span data-ttu-id="b6aa4-108">다음 그림에서는 텍스트 문자열의 내부에 클리핑된 동심 타원의 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6aa4-108">The following illustration shows a set of concentric ellipses clipped to the interior of a string of text.</span></span>  
  
 <span data-ttu-id="b6aa4-109">![제한 된 그리기 화면](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span><span class="sxs-lookup"><span data-stu-id="b6aa4-109">![Restricted Drawing Surface](./media/aboutgdip02-art31.gif "AboutGdip02_Art31")</span></span>  
  
 <span data-ttu-id="b6aa4-110">클리핑을 사용 하 여 그리기를 만들려면를 <xref:System.Drawing.Graphics> 개체, 설정 해당 <xref:System.Drawing.Graphics.Clip%2A> 속성을 동일한 그리기 메서드를 호출 하 고 <xref:System.Drawing.Graphics> 개체:</span><span class="sxs-lookup"><span data-stu-id="b6aa4-110">To draw with clipping, create a <xref:System.Drawing.Graphics> object, set its <xref:System.Drawing.Graphics.Clip%2A> property, and then call the drawing methods of that same <xref:System.Drawing.Graphics> object:</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#91](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## <a name="see-also"></a><span data-ttu-id="b6aa4-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6aa4-111">See also</span></span>

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [<span data-ttu-id="b6aa4-112">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="b6aa4-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="b6aa4-113">영역 사용</span><span class="sxs-lookup"><span data-stu-id="b6aa4-113">Using Regions</span></span>](using-regions.md)
