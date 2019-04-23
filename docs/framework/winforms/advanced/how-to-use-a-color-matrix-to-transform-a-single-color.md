---
title: '방법: 색 매트릭스를 사용하여 단색으로 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 78fc498b0689026fb74ec0c422948c1879495560
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342858"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="2b1c6-102">방법: 색 매트릭스를 사용하여 단색으로 변환</span><span class="sxs-lookup"><span data-stu-id="2b1c6-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2b1c6-103">제공 된 <xref:System.Drawing.Image> 고 <xref:System.Drawing.Bitmap> 저장 및 이미지 조작을 위한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-103">provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="2b1c6-104"><xref:System.Drawing.Image> 및 <xref:System.Drawing.Bitmap> 개체는 32 비트 숫자도 각 픽셀의 색을 저장 합니다. 각각 8 비트가 빨간색, 녹색, 파랑 및 알파에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-104"><xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="2b1c6-105">각 네 가지 구성 요소에는 0부터 농도가 없음을 나타내고 255 전체 강도 나타내는 0부터 255 까지의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="2b1c6-106">색의 투명도 지정 하는 알파 구성 요소: 0은 완전히 투명 하 고 255는 완전히 불투명 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="2b1c6-107">색 벡터는 (빨강, 녹색, 파란색, 알파) 형식의 4 중 튜플입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="2b1c6-108">예를 들어 색 벡터 (0, 255, 0, 255)를 빨강 및 파랑, 녹색 농도가 불투명 한 색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="2b1c6-109">색을 나타내는 다른 규칙에 대 한 전체 강도로 돌아가는 숫자 1을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="2b1c6-110">해당 규칙을 사용 하 여 이전 단락에서 설명한 색을 표시 벡터 (0, 1, 0, 1).</span><span class="sxs-lookup"><span data-stu-id="2b1c6-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="2b1c6-111">색 변환을 수행 하는 경우 전체 강도로 돌아가는으로 1의 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-111">uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="2b1c6-112">4x4 행렬으로 색 벡터를 곱하여 색 벡터로 선형 변환 (회전, 크기 조정 등)를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="2b1c6-113">그러나 비선형 변환을 수행 하는 4x4 행렬을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="2b1c6-114">각 색 벡터에 더미 다섯 번째 좌표 (예를 들어, 숫자 1)을 추가 하는 경우 변환이 선형 조합을 적용할 5 × 5 행렬을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="2b1c6-115">선형 번역 뒤에 변환으로 구성 된 변환에는 3x3 유사 변형을 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="2b1c6-116">예를 들어, (0.2, 0.0, 0.4, 1.0) 색을 사용 하 여 시작한 다음 변환을 적용 하려면:</span><span class="sxs-lookup"><span data-stu-id="2b1c6-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="2b1c6-117">Double 빨강 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2b1c6-117">Double the red component</span></span>  
  
2. <span data-ttu-id="2b1c6-118">0.2 빨강, 녹색 및 파랑 구성 요소에 추가</span><span class="sxs-lookup"><span data-stu-id="2b1c6-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="2b1c6-119">나열 된 순서로 다음 행렬 곱셈 변환이 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 <span data-ttu-id="2b1c6-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span><span class="sxs-lookup"><span data-stu-id="2b1c6-120">![Recoloring](./media/recoloring01.gif "recoloring01")</span></span>  
  
 <span data-ttu-id="2b1c6-121">색 매트릭스의 요소는 행과 열으로 (0부터 시작) 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="2b1c6-122">예를 들어, 다섯 번째 행과 M 행렬의 세 번째 열에 있는 항목은 M [4] [2]에 의해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="2b1c6-123">(다음 그림에 표시) 5 × 5 항등 매트릭스 대각선에는 1 및 0으로 다른 곳에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="2b1c6-124">항등 매트릭스를 색 벡터를 곱하면 색 벡터 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="2b1c6-125">색 변환 행렬을 형성 하는 편리한 방법을 항등 매트릭스로 시작 하 여 필요한 변환을 생성 하는 약간 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 <span data-ttu-id="2b1c6-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span><span class="sxs-lookup"><span data-stu-id="2b1c6-126">![Recoloring](./media/recoloring02.gif "recoloring02")</span></span>  
  
 <span data-ttu-id="2b1c6-127">행렬 및 변환의 자세한 내용은 참조 하세요. [좌표계 및 변형](coordinate-systems-and-transformations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b1c6-128">예제</span><span class="sxs-lookup"><span data-stu-id="2b1c6-128">Example</span></span>  
 <span data-ttu-id="2b1c6-129">다음 예제에서는 모든 하나의 색 (예: 0.2, 0.0, 0.4, 1.0)이 고 이전 단락에 설명 된 변환을 적용 하는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="2b1c6-130">다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지와 변환 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="2b1c6-131">![색](./media/colortrans1.png "colortrans1")</span><span class="sxs-lookup"><span data-stu-id="2b1c6-131">![Colors](./media/colortrans1.png "colortrans1")</span></span>  
  
 <span data-ttu-id="2b1c6-132">다음 예제 코드에서는 다음 단계를 사용 하 여 다시 칠하기는 수행:</span><span class="sxs-lookup"><span data-stu-id="2b1c6-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="2b1c6-133">초기화는 <xref:System.Drawing.Imaging.ColorMatrix> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="2b1c6-134">만들기는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달 합니다 <xref:System.Drawing.Imaging.ColorMatrix> 개체를 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 메서드의 <xref:System.Drawing.Imaging.ImageAttributes> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="2b1c6-135">전달 합니다 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드의 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b1c6-136">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2b1c6-136">Compiling the Code</span></span>  
 <span data-ttu-id="2b1c6-137">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b1c6-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b1c6-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b1c6-138">See also</span></span>

- [<span data-ttu-id="2b1c6-139">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="2b1c6-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="2b1c6-140">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="2b1c6-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
