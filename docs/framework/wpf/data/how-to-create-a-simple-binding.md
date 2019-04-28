---
title: '방법: 단순 바인딩 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: d617c8b97aa679398ed2d061a652f5164f1e499b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931570"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="e060a-102">방법: 단순 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="e060a-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="e060a-103">이 예제에서는 간단한을 만드는 방법을 보여 줍니다. <xref:System.Windows.Data.Binding>합니다.</span><span class="sxs-lookup"><span data-stu-id="e060a-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e060a-104">예제</span><span class="sxs-lookup"><span data-stu-id="e060a-104">Example</span></span>  
 <span data-ttu-id="e060a-105">이 예제는 `Person` 이라는 문자열 속성을 사용 하 여 개체 `PersonName`합니다.</span><span class="sxs-lookup"><span data-stu-id="e060a-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="e060a-106">합니다 `Person` 개체가 이라는 네임 스페이스에 정의 된 `SDKSample`합니다.</span><span class="sxs-lookup"><span data-stu-id="e060a-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="e060a-107">포함 하는 강조 표시 된 줄을 `<src>` 다음 예제에서 요소를 인스턴스화하는 `Person` 개체를 `PersonName` 속성 값 `Joe`합니다.</span><span class="sxs-lookup"><span data-stu-id="e060a-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="e060a-108">이렇게 합니다 `Resources` 섹션 및 할당을 `x:Key`합니다.</span><span class="sxs-lookup"><span data-stu-id="e060a-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="e060a-109">포함 하는 강조 표시 된 줄을 `<TextBlock>` 바인딩합니다 요소를 <xref:System.Windows.Controls.TextBlock> 컨트롤을 `PersonName` 속성.</span><span class="sxs-lookup"><span data-stu-id="e060a-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="e060a-110">결과적으로 <xref:System.Windows.Controls.TextBlock> "Joe" 값으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e060a-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e060a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="e060a-111">See also</span></span>

- [<span data-ttu-id="e060a-112">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="e060a-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="e060a-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="e060a-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
