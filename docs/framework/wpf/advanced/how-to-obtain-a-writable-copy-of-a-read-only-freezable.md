---
title: '방법: 읽기 전용 Freezable의 쓰기 가능한 복사본 가져오기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cloning Freezable objects [WPF]
- Freezable objects [WPF], modifiable clones
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
ms.openlocfilehash: 08b7007911d15019c043a74e093ccc0fba072fd1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361618"
---
# <a name="how-to-obtain-a-writable-copy-of-a-read-only-freezable"></a><span data-ttu-id="69aed-102">방법: 읽기 전용 Freezable의 쓰기 가능한 복사본 가져오기</span><span class="sxs-lookup"><span data-stu-id="69aed-102">How to: Obtain a Writable Copy of a Read-Only Freezable</span></span>
<span data-ttu-id="69aed-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Freezable.Clone%2A> 메서드는 읽기 전용의 쓰기 가능한 복사본을 만드는 <xref:System.Windows.Freezable>합니다.</span><span class="sxs-lookup"><span data-stu-id="69aed-103">This example shows how to use the <xref:System.Windows.Freezable.Clone%2A> method to create a writable copy of a read-only <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="69aed-104">뒤를 <xref:System.Windows.Freezable> 개체가 표시 된 읽기 전용 ("고정")으로 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69aed-104">After a <xref:System.Windows.Freezable> object is marked as read-only ("frozen"), you cannot modify it.</span></span> <span data-ttu-id="69aed-105">그러나 사용할 수는 <xref:System.Windows.Freezable.Clone%2A> 고정된 된 개체의 수정 가능한 복제본을 만드는 방법.</span><span class="sxs-lookup"><span data-stu-id="69aed-105">However, you can use the <xref:System.Windows.Freezable.Clone%2A> method to create a modifiable clone of the frozen object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69aed-106">예제</span><span class="sxs-lookup"><span data-stu-id="69aed-106">Example</span></span>  
 <span data-ttu-id="69aed-107">다음 예제에서는 고정 된의 수정 가능한 복제본을 <xref:System.Windows.Media.SolidColorBrush> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="69aed-107">The following example creates a modifiable clone of a frozen <xref:System.Windows.Media.SolidColorBrush> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 <span data-ttu-id="69aed-108">에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](freezable-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69aed-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69aed-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="69aed-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CloneCurrentValue%2A>
- [<span data-ttu-id="69aed-110">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="69aed-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="69aed-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="69aed-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
