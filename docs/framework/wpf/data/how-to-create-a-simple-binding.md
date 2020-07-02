---
title: '방법: 단순 바인딩 만들기'
description: Windows Presentation Foundation (WPF)에서이 방법 예제를 통해 응용 프로그램에 대 한 간단한 바인딩을 만듭니다.
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618703"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="df9bc-103">방법: 단순 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="df9bc-103">How to: Create a Simple Binding</span></span>
<span data-ttu-id="df9bc-104">이 예제에서는 간단한을 만드는 방법을 보여 줍니다 <xref:System.Windows.Data.Binding> .</span><span class="sxs-lookup"><span data-stu-id="df9bc-104">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df9bc-105">예제</span><span class="sxs-lookup"><span data-stu-id="df9bc-105">Example</span></span>  
 <span data-ttu-id="df9bc-106">이 예제에서는 `Person` 라는 문자열 속성이 있는 개체가 있습니다 `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="df9bc-106">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="df9bc-107">`Person`개체는 라는 네임 스페이스에 정의 됩니다 `SDKSample` .</span><span class="sxs-lookup"><span data-stu-id="df9bc-107">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="df9bc-108">다음 예제에서 요소를 포함 하는 강조 표시 된 줄은 `<src>` `Person` `PersonName` 의 속성 값을 사용 하 여 개체를 인스턴스화합니다 `Joe` .</span><span class="sxs-lookup"><span data-stu-id="df9bc-108">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="df9bc-109">이 작업은 섹션에서 수행 되 `Resources` 고가 할당 됩니다 `x:Key` .</span><span class="sxs-lookup"><span data-stu-id="df9bc-109">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="df9bc-110">요소를 포함 하는 강조 표시 된 줄은 `<TextBlock>` <xref:System.Windows.Controls.TextBlock> 컨트롤을 속성에 바인딩합니다 `PersonName` .</span><span class="sxs-lookup"><span data-stu-id="df9bc-110">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="df9bc-111">그 결과 <xref:System.Windows.Controls.TextBlock> "Joe" 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9bc-111">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9bc-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="df9bc-112">See also</span></span>

- [<span data-ttu-id="df9bc-113">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="df9bc-113">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="df9bc-114">방법 도움말 항목</span><span class="sxs-lookup"><span data-stu-id="df9bc-114">How-to Topics</span></span>](data-binding-how-to-topics.md)
