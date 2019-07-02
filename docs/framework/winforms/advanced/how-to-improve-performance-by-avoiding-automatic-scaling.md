---
title: '방법: 자동 배율 조정 없이 성능 향상'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506211"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="de5f6-102">방법: 자동 배율 조정 없이 성능 향상</span><span class="sxs-lookup"><span data-stu-id="de5f6-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
<span data-ttu-id="de5f6-103">GDI + 그리면, 성능 저하가 발생 하는 이미지를 확장 자동으로 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-103">GDI+ may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="de5f6-104">대상 사각형의 크기를 전달 하 여 이미지의 크기 조정은 제어할 수는 또는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="de5f6-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="de5f6-105">다음을 호출 하는 예를 들어를 <xref:System.Drawing.Graphics.DrawImage%2A> 의 왼쪽 위 모퉁이 지정 하는 메서드 (50, 30) 하지만 대상 사각형을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="de5f6-106">이 가장 쉬운 버전의는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 반드시 가장 효율적인 있지 필요한 인수 개수를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="de5f6-107">GDI + (일반적으로 인치당 96 도트)에서 사용 하는 해상도에 저장 된 해상도와 다른 경우는 <xref:System.Drawing.Image> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 이미지 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-107">If the resolution used by GDI+ (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="de5f6-108">예를 들어는 <xref:System.Drawing.Image> 216 픽셀 너비, 72 인치당 저장된 수평 해상도 값 개체에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="de5f6-109">216/72 3 이므로 <xref:System.Drawing.Graphics.DrawImage%2A> 3 인치 너비 인치당 96 도트의 해상도로 포함 되도록 이미지 크기 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="de5f6-110">즉, <xref:System.Drawing.Graphics.DrawImage%2A> 96 x 3 = 288 개의 너비는 이미지가 표시 됩니다 (픽셀)입니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="de5f6-111">화면 해상도 96dpi 인 다른, 경우에 GDI +는 아마도 이미지 배율을 조정 화면 해상도 96dpi 인 경우.</span><span class="sxs-lookup"><span data-stu-id="de5f6-111">Even if your screen resolution is different from 96 dots per inch, GDI+ will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="de5f6-112">있기 때문입니다 GDI + <xref:System.Drawing.Graphics> 개체가 연결 된 장치 컨텍스트에 및 화면 해상도 대 한 장치 컨텍스트에 GDI + 쿼리 하는 경우 결과 일반적으로 실제 화면 해상도 관계 없이 96입니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-112">That is because a GDI+ <xref:System.Drawing.Graphics> object is associated with a device context, and when GDI+ queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="de5f6-113">대상 사각형을 지정 하 여 자동 크기 조정 하지 않아도 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="de5f6-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de5f6-114">예제</span><span class="sxs-lookup"><span data-stu-id="de5f6-114">Example</span></span>  
 <span data-ttu-id="de5f6-115">다음 예제에서는 두 번 동일한 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-115">The following example draws the same image twice.</span></span> <span data-ttu-id="de5f6-116">첫 번째 경우, 대상 사각형의 높이 너비를 지정 하지 않으면 및 이미지 자동으로 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="de5f6-117">두 번째 경우에서 너비와 대상 사각형의 높이 (픽셀)을 원본 이미지의 높이 너비와 동일 하 게 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="de5f6-118">다음 그림에서는 두 번 렌더링 되는 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-118">The following illustration shows the image rendered twice:</span></span>  
  
 ![배율 조정 된 질감을 사용 하 여 이미지를 보여 주는 스크린샷.](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de5f6-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="de5f6-120">Compiling the Code</span></span>  
 <span data-ttu-id="de5f6-121">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="de5f6-122">Texture.jpg을 이미지 이름 및 시스템에 유효한 경로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="de5f6-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de5f6-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="de5f6-123">See also</span></span>

- [<span data-ttu-id="de5f6-124">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="de5f6-124">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="de5f6-125">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="de5f6-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
