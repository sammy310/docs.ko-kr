---
title: '방법: 메타파일 로드 및 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424814"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="aa2c3-102">방법: 메타파일 로드 및 표시</span><span class="sxs-lookup"><span data-stu-id="aa2c3-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="aa2c3-103"><xref:System.Drawing.Image> 클래스에서 상속 되는 <xref:System.Drawing.Imaging.Metafile> 클래스는 벡터 이미지를 기록, 표시 및 검사 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa2c3-104">예제</span><span class="sxs-lookup"><span data-stu-id="aa2c3-104">Example</span></span>  
 <span data-ttu-id="aa2c3-105">화면에 벡터 이미지 (메타 파일)를 표시 하려면 <xref:System.Drawing.Imaging.Metafile> 개체와 <xref:System.Drawing.Graphics> 개체가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="aa2c3-106">파일 (또는 스트림)의 이름을 <xref:System.Drawing.Imaging.Metafile> 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="aa2c3-107"><xref:System.Drawing.Imaging.Metafile> 개체를 만든 후에는 해당 <xref:System.Drawing.Imaging.Metafile> 개체를 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="aa2c3-108">이 예제에서는 EMF (확장 메타 파일) 파일에서 <xref:System.Drawing.Imaging.Metafile> 개체를 만든 다음 (60, 10)의 왼쪽 위 모퉁이가 포함 된 이미지를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="aa2c3-109">다음 그림에서는 지정 된 위치에 그려진 메타 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="aa2c3-110">![이미지 위치를 보여 주는 스크린샷](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="aa2c3-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="aa2c3-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="aa2c3-111">Compiling the Code</span></span>  
 <span data-ttu-id="aa2c3-112">위의 예제는 Windows Forms와 함께 사용 하도록 설계 되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa2c3-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2c3-113">참조</span><span class="sxs-lookup"><span data-stu-id="aa2c3-113">See also</span></span>

- [<span data-ttu-id="aa2c3-114">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="aa2c3-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
