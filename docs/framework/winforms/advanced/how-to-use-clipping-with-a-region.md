---
title: '방법: 영역에 클리핑 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: cf60b32df805a49f8da2760332dc32e34209f6dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163737"
---
# <a name="how-to-use-clipping-with-a-region"></a><span data-ttu-id="88f03-102">방법: 영역에 클리핑 사용</span><span class="sxs-lookup"><span data-stu-id="88f03-102">How to: Use Clipping with a Region</span></span>
<span data-ttu-id="88f03-103">속성 중 하나는 <xref:System.Drawing.Graphics> 클래스의 클립 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-103">One of the properties of the <xref:System.Drawing.Graphics> class is the clip region.</span></span> <span data-ttu-id="88f03-104">수행한 모든 그리기는 주어진 <xref:System.Drawing.Graphics> 개체의 클립 영역으로 제한 됩니다 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-104">All drawing done by a given <xref:System.Drawing.Graphics> object is restricted to the clip region of that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="88f03-105">호출 하 여 클립 영역을 설정할 수 있습니다는 <xref:System.Drawing.Graphics.SetClip%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="88f03-105">You can set the clip region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88f03-106">예제</span><span class="sxs-lookup"><span data-stu-id="88f03-106">Example</span></span>  
 <span data-ttu-id="88f03-107">다음 예제에서는 단일 다각형으로 구성 된 경로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-107">The following example constructs a path that consists of a single polygon.</span></span> <span data-ttu-id="88f03-108">다음 코드를 해당 경로 기반으로 영역을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-108">Then the code constructs a region, based on that path.</span></span> <span data-ttu-id="88f03-109">지역에 전달 되는 <xref:System.Drawing.Graphics.SetClip%2A> 메서드는 <xref:System.Drawing.Graphics> 개체와 다음 두 문자열을 그릴 합니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-109">The region is passed to the <xref:System.Drawing.Graphics.SetClip%2A> method of a <xref:System.Drawing.Graphics> object, and then two strings are drawn.</span></span>  
  
 <span data-ttu-id="88f03-110">다음 그림은 잘린된 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-110">The following illustration shows the clipped strings.</span></span>  
  
 <span data-ttu-id="88f03-111">![클립](./media/clip1.png "clip1")</span><span class="sxs-lookup"><span data-stu-id="88f03-111">![Clip](./media/clip1.png "clip1")</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88f03-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="88f03-112">Compiling the Code</span></span>  
 <span data-ttu-id="88f03-113">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="88f03-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88f03-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="88f03-114">See also</span></span>

- [<span data-ttu-id="88f03-115">GDI+의 영역</span><span class="sxs-lookup"><span data-stu-id="88f03-115">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="88f03-116">영역 사용</span><span class="sxs-lookup"><span data-stu-id="88f03-116">Using Regions</span></span>](using-regions.md)
