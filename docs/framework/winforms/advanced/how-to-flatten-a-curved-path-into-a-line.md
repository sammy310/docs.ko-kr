---
title: '방법: 구부러진 경로를 선으로 펴기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: a151b4244e14d3704fd5fa1c55de92211981232f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215159"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="8d117-102">방법: 구부러진 경로를 선으로 펴기</span><span class="sxs-lookup"><span data-stu-id="8d117-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="8d117-103"><xref:System.Drawing.Drawing2D.GraphicsPath> 선 및 3 차원 곡선 스플라인의 시퀀스를 저장 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8d117-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="8d117-104">여러 종류의 곡선 (줄임표, 원호를 카디 날 곡선 스플라인) 경로 추가할 수 있지만 경로에 저장 되기 전에 각 곡선을 베 지 어 스플라인을 변환할 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d117-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="8d117-105">경로 평면화 하는 작업은 경로 있는 각 베 지 어 스플라인을 직선 시퀀스로 변환 하는 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d117-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="8d117-106">다음 그림에서는 전후의 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d117-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="8d117-107">![직선 및 곡선](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="8d117-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="8d117-108">경로 평면화 하려면</span><span class="sxs-lookup"><span data-stu-id="8d117-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="8d117-109">호출 된 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 메서드는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8d117-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="8d117-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 메서드는 결합 된 경로 원래 경로 간의 최대 거리를 지정 하는 직선 화 정도 인수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8d117-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d117-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d117-111">See also</span></span>

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="8d117-112">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="8d117-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="8d117-113">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="8d117-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
