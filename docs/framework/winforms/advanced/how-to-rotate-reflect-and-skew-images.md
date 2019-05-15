---
title: '방법: 이미지 회전, 반사 및 기울이기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 80ac92d545d9be7a4a611038eaaadbbdbe2e8ecf
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590332"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="a2d9e-102">방법: 이미지 회전, 반사 및 기울이기</span><span class="sxs-lookup"><span data-stu-id="a2d9e-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="a2d9e-103">회전, 반사 하 고 원본 이미지의 왼쪽 위, 오른쪽 위 및 왼쪽 아래 모퉁이 대 한 대상 점을 지정 하 여 이미지를 기울일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="a2d9e-104">세 개의 대상 지점 원본 사각형이 이미지는 평행 사변형에 매핑되는 3x3 유사 변형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2d9e-105">예제</span><span class="sxs-lookup"><span data-stu-id="a2d9e-105">Example</span></span>  
 <span data-ttu-id="a2d9e-106">예를 들어, 원본 이미지는 사각형의 왼쪽 위 모퉁이 사용 하 여 (0, 0), 오른쪽 위 모서리에서 (100, 0) 하 고 왼쪽 아래 모서리에서 (0, 50).</span><span class="sxs-lookup"><span data-stu-id="a2d9e-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="a2d9e-107">이제 이러한 매핑 한다고 가정 3 가리킵니다 대상 점을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="a2d9e-108">원래 지점</span><span class="sxs-lookup"><span data-stu-id="a2d9e-108">Original point</span></span>|<span data-ttu-id="a2d9e-109">대상 지점</span><span class="sxs-lookup"><span data-stu-id="a2d9e-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="a2d9e-110">왼쪽 위 (0, 0)</span><span class="sxs-lookup"><span data-stu-id="a2d9e-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="a2d9e-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="a2d9e-111">(200, 20)</span></span>|  
|<span data-ttu-id="a2d9e-112">오른쪽 위 (100, 0)</span><span class="sxs-lookup"><span data-stu-id="a2d9e-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="a2d9e-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="a2d9e-113">(110, 100)</span></span>|  
|<span data-ttu-id="a2d9e-114">왼쪽 (0, 50)</span><span class="sxs-lookup"><span data-stu-id="a2d9e-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="a2d9e-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="a2d9e-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="a2d9e-116">다음 그림에서는 원본 이미지와 평행 사변형으로 매핑되는 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="a2d9e-117">원래 이미지 기울이기, 반영, 회전 되어 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="a2d9e-118">실행 하는 줄에 매핑된 원본 이미지의 위쪽 가장자리를 따라 x 축 (200, 20) 및 (110, 100).</span><span class="sxs-lookup"><span data-stu-id="a2d9e-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="a2d9e-119">원본 이미지의 왼쪽된 가장자리를 따라 y 축을 통해 실행 되는 줄에 매핑된 (200, 20) 및 (250, 30).</span><span class="sxs-lookup"><span data-stu-id="a2d9e-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 ![원본 이미지와 이미지는 평행 사변형에 매핑됩니다.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 <span data-ttu-id="a2d9e-121">다음 그림에서는 사진 이미지에 적용할 비슷한 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-121">The following illustration shows a similar transformation applied to a photographic image:</span></span>  
  
 ![오르기와 평행 사변형에 매핑된 그림의 사진입니다.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 <span data-ttu-id="a2d9e-123">다음 그림에서는 이와 유사한 메타 파일에 적용할 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-123">The following illustration shows a similar transformation applied to a metafile:</span></span>  
  
 ![도형 및 텍스트와 평행 사변형으로 매핑되는 그림입니다.](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 <span data-ttu-id="a2d9e-125">다음 예제에서는 첫 번째 그림에 표시 된 이미지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2d9e-126">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a2d9e-126">Compiling the Code</span></span>  
 <span data-ttu-id="a2d9e-127">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="a2d9e-128">바꿔야 `Stripes.bmp` 은 시스템에서 사용할 수 있는 이미지에 경로 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d9e-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d9e-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="a2d9e-129">See also</span></span>

- [<span data-ttu-id="a2d9e-130">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="a2d9e-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
