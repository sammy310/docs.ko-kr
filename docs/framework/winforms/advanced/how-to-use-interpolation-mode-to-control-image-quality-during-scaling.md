---
title: '방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 75f5077c2d969f026a28834144c219f289843dd6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080984"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="b5e57-102">방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리</span><span class="sxs-lookup"><span data-stu-id="b5e57-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="b5e57-103">보간 모드를 <xref:System.Drawing.Graphics> 방식에 영향을 미칩니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 확장 (확장 및 축소) 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="b5e57-104"><xref:System.Drawing.Drawing2D.InterpolationMode> 열거형은 다음 목록에 나와 있는 여러 보간 모드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="b5e57-105">이미지를 확대 하려면 원본 이미지의 각 픽셀의 더 큰 이미지 픽셀 그룹에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="b5e57-106">이미지를 축소 하려면 원래 이미지의 픽셀의 그룹을 더 작은 이미지의 단일 픽셀에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="b5e57-107">이러한 매핑을 수행 하는 알고리즘의 효과 배율 조정 된 이미지의 품질을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="b5e57-108">처리 시간이 더 높은 배율 조정 된 이미지를 생성 하는 알고리즘은 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="b5e57-109">위의 목록에서 <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> 최저 품질 모드 및 <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> 최고 품질 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="b5e57-110">보간 모드를 설정 하려면의 구성원 중 하나를 할당 합니다 <xref:System.Drawing.Drawing2D.InterpolationMode> 열거형을를 <xref:System.Drawing.Graphics.InterpolationMode%2A> 의 속성을 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5e57-111">예제</span><span class="sxs-lookup"><span data-stu-id="b5e57-111">Example</span></span>  
 <span data-ttu-id="b5e57-112">다음 예제에서는 이미지를 그린 다음 세 가지 서로 다른 보간 모드를 사용 하 여 이미지를 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="b5e57-113">다음 그림에서는 원본 이미지와 3 개의 더 작은 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 ![다양 한 보간 설정을 사용 하 여 이미지를 보여 주는 스크린샷.](./media/how-to-use-interpolation-mode-to-control-image-quality-during-scaling/varied-interpolation-settings.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5e57-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b5e57-115">Compiling the Code</span></span>  
 <span data-ttu-id="b5e57-116">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b5e57-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5e57-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b5e57-117">See also</span></span>

- [<span data-ttu-id="b5e57-118">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="b5e57-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="b5e57-119">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="b5e57-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
