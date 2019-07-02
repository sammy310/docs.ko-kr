---
title: 펜을 사용하여 선과 도형 그리기
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: d20b4e47c9f8a5dd7a144e6ebb3151d3ab65a800
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505146"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="433ea-102">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="433ea-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="433ea-103">GDI +를 사용 하 여 `Pen` 선 세그먼트, 곡선 및 도형의 윤곽선을 그릴 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-103">Use GDI+ `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="433ea-104">이 단원의 *줄* 선분을 의미를 지정 하지 않으면 이러한를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="433ea-105">색, 너비, 맞춤 및 해당 펜을 사용 하 여 그리는 선의 스타일을 제어 하는 펜의 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="433ea-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="433ea-106">In This Section</span></span>  
 [<span data-ttu-id="433ea-107">방법: 선을 그리는 펜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="433ea-108">선을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="433ea-109">방법: 펜을 사용 하 여 사각형을 그릴 수</span><span class="sxs-lookup"><span data-stu-id="433ea-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="433ea-110">사각형을 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="433ea-111">방법: 집합 펜 굵기 및 맞춤</span><span class="sxs-lookup"><span data-stu-id="433ea-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="433ea-112">너비 및 맞춤을 변경 하는 방법에 설명 된 `Pen` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="433ea-113">방법: 선 끝이 있는 선 그리기</span><span class="sxs-lookup"><span data-stu-id="433ea-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="433ea-114">선을 그릴 때 끝 캡을 추가 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="433ea-115">방법: 선 조인</span><span class="sxs-lookup"><span data-stu-id="433ea-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="433ea-116">두 줄을 조인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="433ea-117">방법: 사용자 지정 파선 그리기</span><span class="sxs-lookup"><span data-stu-id="433ea-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="433ea-118">파선 그리기 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="433ea-119">방법: 질감으로 채워진 선 그리기</span><span class="sxs-lookup"><span data-stu-id="433ea-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="433ea-120">질감으로 채워진 선 그리기 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="433ea-121">참조</span><span class="sxs-lookup"><span data-stu-id="433ea-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="433ea-122">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="433ea-122">Describes this class and has links to all its members.</span></span>
