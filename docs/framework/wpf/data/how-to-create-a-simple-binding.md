---
title: '방법: 단순 바인딩 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453504"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="9fc93-102">방법: 단순 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="9fc93-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="9fc93-103">이 예에서는 간단한 <xref:System.Windows.Data.Binding>을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fc93-104">예제</span><span class="sxs-lookup"><span data-stu-id="9fc93-104">Example</span></span>  
 <span data-ttu-id="9fc93-105">이 예제에서는 `PersonName`라는 문자열 속성을 사용 하는 `Person` 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="9fc93-106">`Person` 개체는 `SDKSample`라는 네임 스페이스에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="9fc93-107">다음 예제에서 `<src>` 요소를 포함 하는 강조 표시 된 줄은 `Joe`의 `PersonName` 속성 값을 사용 하 여 `Person` 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="9fc93-108">`Resources` 섹션에서 수행 되 고 `x:Key`할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="9fc93-109">`<TextBlock>` 요소를 포함 하는 강조 표시 된 줄은 <xref:System.Windows.Controls.TextBlock> 컨트롤을 `PersonName` 속성에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="9fc93-110">결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값과 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fc93-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc93-111">참조</span><span class="sxs-lookup"><span data-stu-id="9fc93-111">See also</span></span>

- [<span data-ttu-id="9fc93-112">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="9fc93-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9fc93-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="9fc93-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
