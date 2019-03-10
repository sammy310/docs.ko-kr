---
title: '방법: 색 전단'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: eff468e5761038723e16eddf84bdcf8849ac30d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720227"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="8fb2c-102">방법: 색 전단</span><span class="sxs-lookup"><span data-stu-id="8fb2c-102">How to: Shear Colors</span></span>
<span data-ttu-id="8fb2c-103">기울이기 증가 또는 색 구성 요소를 다른 색 구성 요소에 비례 하는 양을 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="8fb2c-104">예를 들어 빨강 구성 요소를 0.5 파랑 구성 요소 값 만큼 늘리는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="8fb2c-105">이러한 변환에서 (0.2, 0.5, 1) 색 (0.7, 0.5, 1) 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="8fb2c-106">새 빨강 구성 요소는 0.2 + (1/2)(1) 0.7입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fb2c-107">예제</span><span class="sxs-lookup"><span data-stu-id="8fb2c-107">Example</span></span>  
 <span data-ttu-id="8fb2c-108">다음 예제에서는 생성 된 <xref:System.Drawing.Image> ColorBars4.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="8fb2c-109">다음 코드는 각 픽셀 이미지에 이전 단락에 설명 된 기울이기 변환을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="8fb2c-110">다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지와 기울이기가 적용 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="8fb2c-111">![색 전단](./media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="8fb2c-111">![Shear Colors](./media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="8fb2c-112">다음 표에서 전과 기울이기 변환 후 4 개 막대에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="8fb2c-113">원래 색</span><span class="sxs-lookup"><span data-stu-id="8fb2c-113">Original</span></span>|<span data-ttu-id="8fb2c-114">전단</span><span class="sxs-lookup"><span data-stu-id="8fb2c-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="8fb2c-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="8fb2c-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="8fb2c-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="8fb2c-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="8fb2c-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="8fb2c-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="8fb2c-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="8fb2c-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="8fb2c-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8fb2c-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8fb2c-123">Compiling the Code</span></span>  
 <span data-ttu-id="8fb2c-124">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="8fb2c-125">대체 `ColorBars.bmp` 있는 이미지 이름 및 경로 시스템에서 사용할 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb2c-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb2c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="8fb2c-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="8fb2c-127">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="8fb2c-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="8fb2c-128">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="8fb2c-128">Recoloring Images</span></span>](recoloring-images.md)
