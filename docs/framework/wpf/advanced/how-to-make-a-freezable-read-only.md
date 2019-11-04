---
title: '방법: Freezable을 읽기 전용으로 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460076"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="90058-102">방법: Freezable을 읽기 전용으로 설정</span><span class="sxs-lookup"><span data-stu-id="90058-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="90058-103">이 예제에서는 <xref:System.Windows.Freezable.Freeze%2A> 메서드를 호출 하 여 <xref:System.Windows.Freezable> 읽기 전용으로 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90058-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="90058-104">다음 조건 중 하나에 개체에 대 한 `true` 있는 경우 <xref:System.Windows.Freezable> 개체를 고정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90058-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="90058-105">애니메이션 또는 데이터 바인딩된 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90058-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="90058-106">동적 리소스에 의해 설정 되는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90058-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="90058-107">동적 리소스에 대 한 자세한 내용은 [XAML 리소스](../../../desktop-wpf/fundamentals/xaml-resources-define.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90058-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="90058-108">고정할 수 없는 <xref:System.Windows.Freezable> 하위 개체가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90058-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="90058-109">이러한 조건이 <xref:System.Windows.Freezable> 개체에 대해 `false` 되 고 수정 하지 않으려는 경우 성능 향상을 위해 고정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="90058-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90058-110">예제</span><span class="sxs-lookup"><span data-stu-id="90058-110">Example</span></span>  
 <span data-ttu-id="90058-111">다음 예에서는 <xref:System.Windows.Freezable> 개체의 형식인 <xref:System.Windows.Media.SolidColorBrush>를 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90058-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="90058-112"><xref:System.Windows.Freezable> 개체에 대 한 자세한 내용은 [Freezable 개체 개요](freezable-objects-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90058-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90058-113">참조</span><span class="sxs-lookup"><span data-stu-id="90058-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="90058-114">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="90058-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="90058-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="90058-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
