---
title: 변형을 사용하여 색의 비율 조정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: ea4abc38968b929412945cddaca3ca3fe6f377d6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707432"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="e4631-102">변형을 사용하여 색의 비율 조정</span><span class="sxs-lookup"><span data-stu-id="e4631-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="e4631-103">배율 조정 변환 이상의 숫자로 된 네 가지 구성 요소를 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="e4631-104">크기 조정 여부를 나타내는 색 매트릭스 항목은 다음 표에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="e4631-105">확장 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e4631-105">Component to be scaled</span></span>|<span data-ttu-id="e4631-106">행렬 항목</span><span class="sxs-lookup"><span data-stu-id="e4631-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="e4631-107">빨강</span><span class="sxs-lookup"><span data-stu-id="e4631-107">Red</span></span>|<span data-ttu-id="e4631-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="e4631-108">[0][0]</span></span>|  
|<span data-ttu-id="e4631-109">녹색</span><span class="sxs-lookup"><span data-stu-id="e4631-109">Green</span></span>|<span data-ttu-id="e4631-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="e4631-110">[1][1]</span></span>|  
|<span data-ttu-id="e4631-111">파랑</span><span class="sxs-lookup"><span data-stu-id="e4631-111">Blue</span></span>|<span data-ttu-id="e4631-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="e4631-112">[2][2]</span></span>|  
|<span data-ttu-id="e4631-113">알파</span><span class="sxs-lookup"><span data-stu-id="e4631-113">Alpha</span></span>|<span data-ttu-id="e4631-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="e4631-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="e4631-115">한 가지 색을 크기 조정</span><span class="sxs-lookup"><span data-stu-id="e4631-115">Scaling One Color</span></span>  
 <span data-ttu-id="e4631-116">다음 예제에서는 생성 된 <xref:System.Drawing.Image> ColorBars2.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="e4631-117">다음 코드를 배율을 각 픽셀의 파랑 구성 요소 이미지에는 2입니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="e4631-118">변환 된 이미지와 함께 원본 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="e4631-119">다음 그림에서는 오른쪽에서 왼쪽의 원본 이미지와 조정 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="e4631-120">![색 조정](./media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="e4631-120">![Scale Colors](./media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="e4631-121">다음 표에서 파란색 크기 조정 전과 후 4 개 막대에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="e4631-122">네 번째 색 막대의 파랑 구성 요소에서 0.8 0.6을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="e4631-123">있기 때문입니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 결과의 소수 부분에만 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="e4631-124">예를 들어 (2)(0.8) 1.6 = 1.6의 소수 부분은 0.6 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="e4631-125">소수 부분에만 유지 하 고 결과 [0, 1] 간격에서 항상 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="e4631-126">원래 색</span><span class="sxs-lookup"><span data-stu-id="e4631-126">Original</span></span>|<span data-ttu-id="e4631-127">확장</span><span class="sxs-lookup"><span data-stu-id="e4631-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="e4631-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="e4631-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="e4631-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="e4631-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="e4631-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="e4631-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="e4631-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="e4631-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="e4631-136">여러 색 비율 조정</span><span class="sxs-lookup"><span data-stu-id="e4631-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="e4631-137">다음 예제에서는 생성 된 <xref:System.Drawing.Image> ColorBars2.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="e4631-138">다음 코드는 이미지의 각 픽셀의 빨강, 녹색 및 파랑 구성 요소를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="e4631-139">빨강 구성 요소는 25%를 축소 하 고, 35%, 녹색 구성 요소는 확장 한 다음 파란색 구성 요소는 50%를 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="e4631-140">다음 그림에서는 오른쪽에서 왼쪽의 원본 이미지와 조정 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="e4631-141">![색 조정](./media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="e4631-141">![Scale Colors](./media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="e4631-142">다음 표에서 빨강, 녹색 및 파랑 크기 조정 전과 후 4 개 막대에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e4631-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="e4631-143">원래 색</span><span class="sxs-lookup"><span data-stu-id="e4631-143">Original</span></span>|<span data-ttu-id="e4631-144">확장</span><span class="sxs-lookup"><span data-stu-id="e4631-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="e4631-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="e4631-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="e4631-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="e4631-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="e4631-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="e4631-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="e4631-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="e4631-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="e4631-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e4631-153">참고자료</span><span class="sxs-lookup"><span data-stu-id="e4631-153">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="e4631-154">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="e4631-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e4631-155">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="e4631-155">Recoloring Images</span></span>](recoloring-images.md)
