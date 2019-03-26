---
title: '방법: 이미지 색 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 8b2e28cab2d2d04f7c99880f2b35a02ebe80dcd8
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464465"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="16602-102">방법: 이미지 색 변환</span><span class="sxs-lookup"><span data-stu-id="16602-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="16602-103">번역 네 가지 구성 요소 중 하나 이상에 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16602-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="16602-104">번역을 나타내는 색 매트릭스 항목은 다음 표에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16602-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="16602-105">변환 구성 요소</span><span class="sxs-lookup"><span data-stu-id="16602-105">Component to be translated</span></span>|<span data-ttu-id="16602-106">행렬 항목</span><span class="sxs-lookup"><span data-stu-id="16602-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="16602-107">빨강</span><span class="sxs-lookup"><span data-stu-id="16602-107">Red</span></span>|<span data-ttu-id="16602-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="16602-108">[4][0]</span></span>|  
|<span data-ttu-id="16602-109">녹색</span><span class="sxs-lookup"><span data-stu-id="16602-109">Green</span></span>|<span data-ttu-id="16602-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="16602-110">[4][1]</span></span>|  
|<span data-ttu-id="16602-111">파랑</span><span class="sxs-lookup"><span data-stu-id="16602-111">Blue</span></span>|<span data-ttu-id="16602-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="16602-112">[4][2]</span></span>|  
|<span data-ttu-id="16602-113">알파</span><span class="sxs-lookup"><span data-stu-id="16602-113">Alpha</span></span>|<span data-ttu-id="16602-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="16602-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="16602-115">예제</span><span class="sxs-lookup"><span data-stu-id="16602-115">Example</span></span>  
 <span data-ttu-id="16602-116">다음 예제에서는 생성 된 <xref:System.Drawing.Image> ColorBars.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="16602-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="16602-117">다음 코드는 이미지의 각 픽셀의 빨강 구성 요소를 0.75를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16602-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="16602-118">변환 된 이미지와 함께 원본 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="16602-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="16602-119">다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지와 변환 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16602-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![원본 및 변환 된 이미지의 스크린샷입니다.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="16602-121">다음 표에서 빨간색 번역 전후 4 개 막대에 대 한 색 벡터를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="16602-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="16602-122">Note 색 구성 요소에 대 한 최대값은 1 이므로 두 번째 행의 빨강 구성 요소 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16602-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="16602-123">(마찬가지로 색 구성 요소에 대 한 최소값은 0입니다.)</span><span class="sxs-lookup"><span data-stu-id="16602-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="16602-124">원래 색</span><span class="sxs-lookup"><span data-stu-id="16602-124">Original</span></span>|<span data-ttu-id="16602-125">번역 언어</span><span class="sxs-lookup"><span data-stu-id="16602-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="16602-126">검은색 (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="16602-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="16602-128">빨강 (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="16602-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="16602-130">녹색 (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="16602-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="16602-132">(0, 0, 1, 1) 파랑</span><span class="sxs-lookup"><span data-stu-id="16602-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="16602-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="16602-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16602-134">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="16602-134">Compiling the Code</span></span>  
 <span data-ttu-id="16602-135">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="16602-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="16602-136">대체 `ColorBars.bmp` 있는 이미지 파일 이름 및 경로 시스템에서 사용할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="16602-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16602-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="16602-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="16602-138">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="16602-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="16602-139">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="16602-139">Recoloring Images</span></span>](recoloring-images.md)
