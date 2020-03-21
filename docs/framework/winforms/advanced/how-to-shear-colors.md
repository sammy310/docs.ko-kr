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
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142396"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="45ec9-102">방법: 색 전단</span><span class="sxs-lookup"><span data-stu-id="45ec9-102">How to: Shear Colors</span></span>
<span data-ttu-id="45ec9-103">전단은 다른 색상 구성 요소에 비례하는 양만큼 색상 구성 요소를 증가하거나 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="45ec9-104">예를 들어 빨간색 구성 요소가 파란색 구성 요소값의 절반으로 증가하는 변환을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="45ec9-105">이러한 변환에서 색상(0.2, 0.5, 1)은 (0.7, 0.5, 1)이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="45ec9-106">새 빨간색 구성 요소는 0.2 + (1/2)(1) = 0.7입니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45ec9-107">예제</span><span class="sxs-lookup"><span data-stu-id="45ec9-107">Example</span></span>  
 <span data-ttu-id="45ec9-108">다음 예제는 ColorBars4.bmp 파일에서 <xref:System.Drawing.Image> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="45ec9-109">그런 다음 코드는 앞단락에 설명된 전단 변환을 이미지의 각 픽셀에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="45ec9-110">다음 그림에서는 왼쪽의 원본 이미지와 오른쪽의 전이어 이미지를 보여 주며, 오른쪽은 전이어를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![원본 이미지와 전단 이미지를 보여주는 컬러 줄무늬가 나란히 있는 두 개의 사각형.](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="45ec9-112">다음 표에는 전단 변환 전후의 네 개의 막대에 대한 색상 벡터가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="45ec9-113">Original</span><span class="sxs-lookup"><span data-stu-id="45ec9-113">Original</span></span>|<span data-ttu-id="45ec9-114">전단</span><span class="sxs-lookup"><span data-stu-id="45ec9-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="45ec9-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="45ec9-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="45ec9-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="45ec9-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="45ec9-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="45ec9-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="45ec9-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="45ec9-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="45ec9-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="45ec9-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="45ec9-123">Compiling the Code</span></span>  
 <span data-ttu-id="45ec9-124">앞의 예제는 Windows Forms와 함께 사용하도록 <xref:System.Windows.Forms.PaintEventArgs> `e`설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 이 요구사항입니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="45ec9-125">시스템에서 `ColorBars.bmp` 유효한 이미지 이름과 경로로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="45ec9-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ec9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45ec9-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="45ec9-127">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="45ec9-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="45ec9-128">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="45ec9-128">Recoloring Images</span></span>](recoloring-images.md)
