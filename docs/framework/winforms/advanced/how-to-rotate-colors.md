---
title: '방법: 색 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967355"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="6511b-102">방법: 색 회전</span><span class="sxs-lookup"><span data-stu-id="6511b-102">How to: Rotate Colors</span></span>
<span data-ttu-id="6511b-103">4 차원 색 공간에서 회전은 시각화 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="6511b-104">에서는 수 쉽게 동의 고정 색 구성 요소 중 하나를 유지 하 여 회전을 시각화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="6511b-105">1 자리 알파 구성 요소 (완전 불투명) 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="6511b-106">그런 다음 다음 그림에 나와 있는 것 처럼 빨강, 녹색 및 파랑 축이 있는 3 차원 색 공간을를 시각화할 수 있습니다 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![빨간색, 녹색 및 파란색 축 회전을 보여 주는 그림입니다.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="6511b-108">색을 3 차원 공간에서 지점으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="6511b-109">예를 들어 공간의 점 (1, 0, 0) 빨강을 나타내고 녹색 공간의 점 (0, 1, 0)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="6511b-110">다음 그림에서는 빨간색-녹색 평면에서 60도의 각도 통해 (1, 0, 0) 색을 회전 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="6511b-111">빨강-녹색 평면 평행한 평면에서 회전 파란색 축 회전으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![파란색 축 회전을 보여 주는 그림입니다.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="6511b-113">다음 그림에서는 각각 세 개의 좌표 축 (빨간색, 녹색, 파랑)에 대 한 회전을 수행 하기 위해 색 매트릭스를 초기화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![3 개의 축 중심으로 회전 하는 데 색 매트릭스를 초기화 합니다.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="6511b-115">예제</span><span class="sxs-lookup"><span data-stu-id="6511b-115">Example</span></span>  
 <span data-ttu-id="6511b-116">다음 예제에서는 (1, 0, 0.6) 모두 같은 색은 파란색 축에 대 한 60도 회전을 적용 하는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="6511b-117">회전은 빨강-녹색 평면에 병렬 되는 평면에서 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="6511b-118">다음 그림에서는 왼쪽 및 오른쪽에 있는 색 회전 이미지에 원본 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![원래 이미지와 색 회전 이미지를 보여 주는 그림입니다.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="6511b-120">다음 그림에서는 다음 코드에서 수행 되는 색 회전 시각화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![색 회전 시각화를 보여 주는 그림입니다.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6511b-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6511b-122">Compiling the Code</span></span>  
 <span data-ttu-id="6511b-123">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="6511b-124">대체 `RotationInput.bmp` 와 경로 시스템에서 사용할 이미지 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6511b-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6511b-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="6511b-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="6511b-126">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="6511b-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="6511b-127">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="6511b-127">Recoloring Images</span></span>](recoloring-images.md)
