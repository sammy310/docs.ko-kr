---
title: '방법: 화면에 기존 비트맵 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: d2e06aa382bc2b01a4308f99735ca533e7a9a3ea
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653823"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="28e02-102">방법: 화면에 기존 비트맵 그리기</span><span class="sxs-lookup"><span data-stu-id="28e02-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="28e02-103">쉽게 화면의 기존 이미지를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28e02-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="28e02-104">먼저 만들어야를 <xref:System.Drawing.Bitmap> 파일 이름을 사용 하는 비트맵 생성자를 사용 하 여 개체 <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>합니다.</span><span class="sxs-lookup"><span data-stu-id="28e02-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="28e02-105">이 생성자는 여러 다른 파일 형식으로 BMP, GIF, JPEG, PNG 및 TIFF 등을 사용 하 여 이미지를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="28e02-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="28e02-106">만든 후는 <xref:System.Drawing.Bitmap> 개체를 전달 <xref:System.Drawing.Bitmap> 개체를 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드의 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="28e02-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28e02-107">예제</span><span class="sxs-lookup"><span data-stu-id="28e02-107">Example</span></span>  
 <span data-ttu-id="28e02-108">이 예제에서는 <xref:System.Drawing.Bitmap> JPEG 파일에서 개체 다음에 왼쪽 위 모퉁이 사용 하 여 비트맵을 그립니다 (60, 10).</span><span class="sxs-lookup"><span data-stu-id="28e02-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="28e02-109">다음 그림에서는 지정된 된 위치에 그릴 비트맵을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28e02-109">The following illustration shows the bitmap drawn at the specified location:</span></span>  
  
 ![지정된 된 위치에서 이미지를 보여 주는 스크린샷.](./media/how-to-draw-an-existing-bitmap-to-the-screen/bitmap-specified-position.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="28e02-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="28e02-111">Compiling the Code</span></span>  
 <span data-ttu-id="28e02-112">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="28e02-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e02-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="28e02-113">See also</span></span>
- [<span data-ttu-id="28e02-114">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="28e02-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="28e02-115">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="28e02-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
