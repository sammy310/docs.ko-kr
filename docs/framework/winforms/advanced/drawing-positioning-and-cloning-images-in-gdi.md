---
title: GDI+에서 이미지 그리기, 위치 지정 및 복제
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188450"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="dec1e-102">GDI+에서 이미지 그리기, 위치 지정 및 복제</span><span class="sxs-lookup"><span data-stu-id="dec1e-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="dec1e-103">사용할 수는 <xref:System.Drawing.Bitmap> 로드 래스터 이미지를 표시 하는 클래스를 사용할 수는 <xref:System.Drawing.Imaging.Metafile> 클래스를 로드 하 고 벡터 이미지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="dec1e-104"><xref:System.Drawing.Bitmap> 하 고 <xref:System.Drawing.Imaging.Metafile> 클래스에서 상속 된 <xref:System.Drawing.Image> 클래스.</span><span class="sxs-lookup"><span data-stu-id="dec1e-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="dec1e-105">인스턴스의 벡터 이미지를 표시 하려면 필요 합니다 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Imaging.Metafile>합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="dec1e-106">인스턴스의 래스터 이미지를 표시 하려면 필요 합니다 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Bitmap>합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="dec1e-107">인스턴스의 <xref:System.Drawing.Graphics> 클래스를 제공 합니다 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 수신 하는 합니다 <xref:System.Drawing.Imaging.Metafile> 또는 <xref:System.Drawing.Bitmap> 인수로.</span><span class="sxs-lookup"><span data-stu-id="dec1e-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="dec1e-108">파일 형식 및 복제</span><span class="sxs-lookup"><span data-stu-id="dec1e-108">File Types and Cloning</span></span>  
 <span data-ttu-id="dec1e-109">다음 코드 예제를 생성 하는 방법을 보여 줍니다는 <xref:System.Drawing.Bitmap> Climber.jpg 파일에서 비트맵을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="dec1e-110">이미지의 왼쪽 위 모퉁이 대 한 대상 점 (10, 10)에 두 번째 및 세 번째 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="dec1e-111">다음 그림에서는 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="dec1e-112">![샘플 이미지](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="dec1e-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="dec1e-113">생성할 수 있습니다 <xref:System.Drawing.Bitmap> 다양 한 그래픽 개체 파일 형식: BMP, GIF, JPEG, EXIF, PNG, TIFF 및 아이콘</span><span class="sxs-lookup"><span data-stu-id="dec1e-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="dec1e-114">다음 코드 예제를 생성 하는 방법을 보여 줍니다 <xref:System.Drawing.Bitmap> 다양 한 파일 형식에서에서 개체 및 다음 비트맵을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="dec1e-115"><xref:System.Drawing.Bitmap> 클래스를 제공 된 <xref:System.Drawing.Bitmap.Clone%2A> 의 기존 복사본을 사용할 수 있는 메서드 <xref:System.Drawing.Bitmap>.</span><span class="sxs-lookup"><span data-stu-id="dec1e-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="dec1e-116"><xref:System.Drawing.Bitmap.Clone%2A> 메서드에 복사 하려는 원본 비트맵의 일부를 지정 하는 데 사용할 수 있는 소스 사각형 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="dec1e-117">다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Drawing.Bitmap> 기존의 위쪽 절반을 복제 하 여 <xref:System.Drawing.Bitmap>입니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="dec1e-118">다음 두 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="dec1e-119">다음 그림에서는 두 개의 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dec1e-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="dec1e-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="dec1e-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec1e-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="dec1e-121">See also</span></span>

- [<span data-ttu-id="dec1e-122">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="dec1e-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="dec1e-123">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="dec1e-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="dec1e-124">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="dec1e-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
