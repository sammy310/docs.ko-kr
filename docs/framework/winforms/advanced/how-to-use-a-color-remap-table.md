---
title: '방법: 색 다시 매핑 테이블 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 73f4f19229a31266b406214e93e2b59acd343ca2
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463893"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="3c749-102">방법: 색 다시 매핑 테이블 사용</span><span class="sxs-lookup"><span data-stu-id="3c749-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="3c749-103">다시 매핑하는 프로세스 색 다시 매핑 테이블에 따라 이미지의 색을 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="3c749-104">색 다시 매핑 테이블을 배열이 <xref:System.Drawing.Imaging.ColorMap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3c749-105">각 <xref:System.Drawing.Imaging.ColorMap> 배열의 개체에는 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 속성 및 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="3c749-106">때 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 이전 색 배열을 비교할 이미지의 각 픽셀 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="3c749-107">이전 색상을 픽셀의 색 일치 하는 경우 해당 새로운 색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="3c749-108">색이 렌더링에만 변경 됩니다-이미지 자체의 색상 값 (에 저장 된를 <xref:System.Drawing.Image> 또는 <xref:System.Drawing.Bitmap> 개체)는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="3c749-109">매핑된 이미지를 그릴 배열을 초기화할 <xref:System.Drawing.Imaging.ColorMap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3c749-110">해당 배열을 전달 합니다 <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> 메서드의 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달한를 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드의 <xref:System.Drawing.Graphics> 개체.</span><span class="sxs-lookup"><span data-stu-id="3c749-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c749-111">예제</span><span class="sxs-lookup"><span data-stu-id="3c749-111">Example</span></span>  
 <span data-ttu-id="3c749-112">다음 예제에서는 <xref:System.Drawing.Image> RemapInput.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="3c749-113">코드는 단일 구성 되는 색 다시 매핑 테이블을 만듭니다 <xref:System.Drawing.Imaging.ColorMap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="3c749-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 의 속성을 `ColorRemap` 개체가 빨강, 및 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성이 파란색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="3c749-115">이미지가 그려지는 번 다시 매핑 없이 한 번 다시 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="3c749-116">다시 매핑 프로세스에서 파란색 빨간색 모든 픽셀을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="3c749-117">다음 그림에서는 오른쪽에서 왼쪽의 원래 이미지와 매핑된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![원본 이미지와 매핑된 이미지를 보여주는 스크린샷.](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c749-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3c749-119">Compiling the Code</span></span>  
 <span data-ttu-id="3c749-120">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c749-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c749-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c749-121">See also</span></span>
- [<span data-ttu-id="3c749-122">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="3c749-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="3c749-123">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="3c749-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
