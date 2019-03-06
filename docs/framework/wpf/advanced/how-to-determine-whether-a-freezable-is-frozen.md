---
title: '방법: Freezable의 고정 여부 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], determining if frozen
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
ms.openlocfilehash: 005bb27803830a2e38a7b143d2c4cff669ad1da6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362515"
---
# <a name="how-to-determine-whether-a-freezable-is-frozen"></a><span data-ttu-id="eedc5-102">방법: Freezable의 고정 여부 확인</span><span class="sxs-lookup"><span data-stu-id="eedc5-102">How to: Determine Whether a Freezable Is Frozen</span></span>
<span data-ttu-id="eedc5-103">확인 하는 방법을 보여 주는이 예제 여부는 <xref:System.Windows.Freezable> 개체의 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eedc5-103">This example shows how to determine whether a <xref:System.Windows.Freezable> object is frozen.</span></span> <span data-ttu-id="eedc5-104">고정 된 수정 하려고 하면 <xref:System.Windows.Freezable> 개체를 throw 한 <xref:System.InvalidOperationException>합니다.</span><span class="sxs-lookup"><span data-stu-id="eedc5-104">If you try to modify a frozen <xref:System.Windows.Freezable> object, it throws an <xref:System.InvalidOperationException>.</span></span> <span data-ttu-id="eedc5-105">이 예외를 방지 하려면 사용 합니다 <xref:System.Windows.Freezable.IsFrozen%2A> 의 속성을 <xref:System.Windows.Freezable> 고정 되었는지 여부를 결정 하는 개체.</span><span class="sxs-lookup"><span data-stu-id="eedc5-105">To avoid throwing this exception, use the <xref:System.Windows.Freezable.IsFrozen%2A> property of the <xref:System.Windows.Freezable> object to determine whether it is frozen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eedc5-106">예제</span><span class="sxs-lookup"><span data-stu-id="eedc5-106">Example</span></span>  
 <span data-ttu-id="eedc5-107">다음 예에서는 중지를 <xref:System.Windows.Media.SolidColorBrush> 다음 사용 하 여 테스트를 <xref:System.Windows.Freezable.IsFrozen%2A> 속성의 고정 여부 확인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="eedc5-107">The following example freezes a <xref:System.Windows.Media.SolidColorBrush> and then tests it by using the <xref:System.Windows.Freezable.IsFrozen%2A> property to determine whether it is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="eedc5-108">에 대 한 자세한 내용은 <xref:System.Windows.Freezable> 개체를 참조 합니다 [Freezable 개체 개요](freezable-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eedc5-108">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedc5-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="eedc5-109">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.IsFrozen%2A>
- [<span data-ttu-id="eedc5-110">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="eedc5-110">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="eedc5-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="eedc5-111">How-to Topics</span></span>](base-elements-how-to-topics.md)
