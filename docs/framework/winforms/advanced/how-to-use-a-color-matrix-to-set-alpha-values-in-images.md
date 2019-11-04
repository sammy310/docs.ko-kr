---
title: '방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423732"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="a2a36-102">방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정</span><span class="sxs-lookup"><span data-stu-id="a2a36-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="a2a36-103"><xref:System.Drawing.Image> 클래스에서 상속 되는 <xref:System.Drawing.Bitmap> 클래스 및 <xref:System.Drawing.Imaging.ImageAttributes> 클래스는 픽셀 값을 가져오고 설정 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="a2a36-104"><xref:System.Drawing.Imaging.ImageAttributes> 클래스를 사용 하 여 전체 이미지에 대 한 알파 값을 수정 하거나 <xref:System.Drawing.Bitmap> 클래스의 <xref:System.Drawing.Bitmap.SetPixel%2A> 메서드를 호출 하 여 개별 픽셀 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a36-105">예제</span><span class="sxs-lookup"><span data-stu-id="a2a36-105">Example</span></span>  
 <span data-ttu-id="a2a36-106"><xref:System.Drawing.Imaging.ImageAttributes> 클래스에는 렌더링 중에 이미지를 수정 하는 데 사용할 수 있는 많은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="a2a36-107">다음 예제에서는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 사용 하 여 모든 알파 값을 80%로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="a2a36-108">이 작업은 색 매트릭스를 초기화 하 고 행렬의 알파 크기 조정 값을 0.8로 설정 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="a2a36-109">색 매트릭스의 주소는 <xref:System.Drawing.Imaging.ImageAttributes> 개체의 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 메서드에 전달 되 고 <xref:System.Drawing.Imaging.ImageAttributes> 개체는 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="a2a36-110">렌더링 중에 비트맵의 알파 값은 해당 값의 80%로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="a2a36-111">이렇게 하면 배경으로 혼합 된 이미지가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="a2a36-112">다음 그림에 나와 있는 것 처럼 비트맵 이미지는 투명 하 게 보입니다. 검정의 검정 줄을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="a2a36-113">![행렬을 사용 하는 알파 혼합의 스크린샷](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span><span class="sxs-lookup"><span data-stu-id="a2a36-113">![Screenshot of alpha blending using a matrix.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span></span>  
  
 <span data-ttu-id="a2a36-114">이미지가 배경의 흰색 부분 위에 있는 경우 이미지가 흰색으로 혼합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="a2a36-115">이미지가 검은색 선을 교차할 때 이미지는 검정 색과 혼합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2a36-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a2a36-116">Compiling the Code</span></span>  
 <span data-ttu-id="a2a36-117">위의 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a36-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a36-118">참조</span><span class="sxs-lookup"><span data-stu-id="a2a36-118">See also</span></span>

- [<span data-ttu-id="a2a36-119">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="a2a36-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="a2a36-120">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="a2a36-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
