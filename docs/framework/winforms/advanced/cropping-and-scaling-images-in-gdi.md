---
title: GDI+에서 이미지 자르기 및 배율 조정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: c3cdb06e99770808461f9266fb5f07df9074149b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183731"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="89de1-102">GDI+에서 이미지 자르기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="89de1-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="89de1-103">사용할 수는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드는 <xref:System.Drawing.Graphics> 그리고 이미지 벡터 및 래스터 이미지를 배치 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="89de1-104"><xref:System.Drawing.Graphics.DrawImage%2A> 오버 로드 된 메서드인 이므로 여러 가지 인수를 사용 하 여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="89de1-105">DrawImage 변형</span><span class="sxs-lookup"><span data-stu-id="89de1-105">DrawImage Variations</span></span>  
 <span data-ttu-id="89de1-106">변형 된 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드는 수신를 <xref:System.Drawing.Bitmap> 및 <xref:System.Drawing.Rectangle>합니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="89de1-107">사각형 그리기 작업에 대 한 대상을 지정합니다. 즉, 이미지를 그릴 사각형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="89de1-108">대상 사각형의 크기는 원본 이미지의 크기와 다른 경우 대상 사각형에 맞게 이미지 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="89de1-109">다음 코드 예제에는 세 번 동일한 이미지를 그리는 방법을 보여 줍니다: 크기 조정 없음 번, 확장을 사용 하 여 한 번 및 압축을 사용 하 여 한 번:</span><span class="sxs-lookup"><span data-stu-id="89de1-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="89de1-110">다음 그림에서는 세 가지 그림을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="89de1-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="89de1-111">![Scaling](./media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="89de1-112">일부 변형 된 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드는 대상 사각형 매개 변수 뿐 아니라 소스 사각형 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="89de1-113">그릴 원본 이미지의 부분을 지정 하는 소스 사각형 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="89de1-114">대상 사각형에는 이미지의 해당 부분을 그릴 사각형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="89de1-115">대상 사각형의 크기가 소스 사각형의 크기와 다른 경우에 그림 대상 사각형에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="89de1-116">다음 코드 예제를 생성 하는 방법을 보여 줍니다는 <xref:System.Drawing.Bitmap> Runner.jpg 파일에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="89de1-117">확장에서 사용 하 여 전체 이미지를 그릴 (0, 0).</span><span class="sxs-lookup"><span data-stu-id="89de1-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="89de1-118">다음 이미지의 작은 부분을 두 번 그려집니다: 압축을 사용 하 여 한 번 및 확장을 사용 하 여 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="89de1-119">다음 그림에는 실제 크기의 이미지 및 압축 및 확장 된 이미지 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89de1-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="89de1-120">![자르기 및 배율 조정](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="89de1-120">![Cropping and Scaling](./media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89de1-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="89de1-121">See also</span></span>

- [<span data-ttu-id="89de1-122">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="89de1-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="89de1-123">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="89de1-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
