---
title: '방법: 영역에 적중 테스트 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778874"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="4a30e-102">방법: 영역에 적중 테스트 사용</span><span class="sxs-lookup"><span data-stu-id="4a30e-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="4a30e-103">적중 횟수 테스트의 목적은 커서 아이콘 단추 등의 지정 된 개체에 대해 인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a30e-104">예제</span><span class="sxs-lookup"><span data-stu-id="4a30e-104">Example</span></span>  
 <span data-ttu-id="4a30e-105">다음 예제에서는 두 개의 사각형 영역을 결합 하 여 더하기 모양의 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="4a30e-106">가정 변수의 `point` 최신 클릭의 위치를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="4a30e-107">코드 확인 여부를 `point` 더하기 모양의 지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="4a30e-108">요점은 (적중) 지역의 경우 지역 불투명 빨강 브러시를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="4a30e-109">그렇지 않으면 지역 빨간색 반투명 브러시를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a30e-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4a30e-110">Compiling the Code</span></span>  
 <span data-ttu-id="4a30e-111">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a30e-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a30e-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a30e-112">See also</span></span>

- <xref:System.Drawing.Region>
- [<span data-ttu-id="4a30e-113">GDI+의 영역</span><span class="sxs-lookup"><span data-stu-id="4a30e-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="4a30e-114">방법: 클리핑 영역 사용</span><span class="sxs-lookup"><span data-stu-id="4a30e-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
