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
ms.openlocfilehash: 79937f0801a790d4ff1ab327aaaf45ef1b881827
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199546"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="3f4cd-102">방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정</span><span class="sxs-lookup"><span data-stu-id="3f4cd-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="3f4cd-103">합니다 <xref:System.Drawing.Bitmap> 클래스 (에서 상속 되는 <xref:System.Drawing.Image> 클래스) 및 <xref:System.Drawing.Imaging.ImageAttributes> 가져오고 픽셀 값을 설정 하기 위한 기능을 제공 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="3f4cd-104">사용할 수는 <xref:System.Drawing.Imaging.ImageAttributes> 알파를 수정 하는 클래스는 전체 이미지에 대 한 값 또는 호출할 수 있습니다 합니다 <xref:System.Drawing.Bitmap.SetPixel%2A> 메서드의 <xref:System.Drawing.Bitmap> 개별 픽셀 값을 수정 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f4cd-105">예제</span><span class="sxs-lookup"><span data-stu-id="3f4cd-105">Example</span></span>  
 <span data-ttu-id="3f4cd-106"><xref:System.Drawing.Imaging.ImageAttributes> 클래스에 렌더링 하는 동안 이미지를 수정 하는 데 사용할 수 있는 많은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="3f4cd-107">다음 예제에서는 <xref:System.Drawing.Imaging.ImageAttributes> 개체 어떤의 80%로 모든 알파 값을 설정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="3f4cd-108">색 매트릭스를 초기화 하 고 alpha 행렬 0.8에 있는 값을 크기 조정에 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="3f4cd-109">색 매트릭스의 주소에 전달 되는 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 메서드를 <xref:System.Drawing.Imaging.ImageAttributes> 개체 및 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달 하는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드의 <xref:System.Drawing.Graphics> 개체.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="3f4cd-110">비트맵의 알파 값은 렌더링 하는 동안 어떤의 80%로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="3f4cd-111">이 인해 이미지는 배경색과 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="3f4cd-112">다음 그림에서 알 수 있듯이, 비트맵 이미지가 찾습니다 투명 합니다. 통해 검은 실선이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="3f4cd-113">![행렬을 사용 하 여 알파 혼합](./media/image2.png "이미지 2")</span><span class="sxs-lookup"><span data-stu-id="3f4cd-113">![Alpha Blending Using a Matrix](./media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="3f4cd-114">이미지는 배경의 흰색 부분에 이미지를 흰색으로 혼합 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="3f4cd-115">이미지는 검은색 줄과 교차 검은색 이미지 혼합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f4cd-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3f4cd-116">Compiling the Code</span></span>  
 <span data-ttu-id="3f4cd-117">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs>`e`에서의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="3f4cd-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f4cd-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f4cd-118">See also</span></span>

- [<span data-ttu-id="3f4cd-119">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="3f4cd-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="3f4cd-120">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="3f4cd-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
