---
title: '방법: 종속성 속성 구현'
description: DependencyProperty 필드를 사용 하 여 공용 언어 런타임 속성을 백업 하 여 Windows Presentation Foundation에서 종속성 속성을 정의 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165093"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="57829-103">방법: 종속성 속성 구현</span><span class="sxs-lookup"><span data-stu-id="57829-103">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="57829-104">이 예제에서는 필드를 사용 하 여 CLR (공용 언어 런타임) 속성을 백업 하는 방법을 보여 줍니다 <xref:System.Windows.DependencyProperty> . 따라서 종속성 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="57829-104">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="57829-105">고유 속성을 정의하고 스타일, 데이터 바인딩, 상속, 애니메이션 및 기본값을 포함한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 기능의 여러 측면을 지원하려면 해당 속성을 종속성 속성으로 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57829-105">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57829-106">예제</span><span class="sxs-lookup"><span data-stu-id="57829-106">Example</span></span>  
 <span data-ttu-id="57829-107">다음 예제에서는 먼저 메서드를 호출 하 여 종속성 속성을 등록 합니다 <xref:System.Windows.DependencyProperty.Register%2A> .</span><span class="sxs-lookup"><span data-stu-id="57829-107">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="57829-108">종속성 속성의 이름과 특성을 저장 하는 데 사용 하는 식별자 필드의 이름은 <xref:System.Windows.DependencyProperty.Name%2A> 호출의 일부로 종속성 속성에 대해 선택한입니다 <xref:System.Windows.DependencyProperty.Register%2A> . 이때 리터럴 문자열을 추가 해야 합니다 `Property` .</span><span class="sxs-lookup"><span data-stu-id="57829-108">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="57829-109">예를 들어의를 사용 하 여 종속성 속성을 등록 하는 경우 <xref:System.Windows.DependencyProperty.Name%2A> `Location` 종속성 속성에 대해 정의 하는 식별자 필드의 이름을로 지정 해야 합니다 `LocationProperty` .</span><span class="sxs-lookup"><span data-stu-id="57829-109">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="57829-110">이 예제에서 종속성 속성의 이름과 CLR 접근자는입니다. 식별자 필드는이 고, `State` `StateProperty` 속성의 형식은이 고, <xref:System.Boolean> 종속성 속성을 등록 하는 형식은입니다 `MyStateControl` .</span><span class="sxs-lookup"><span data-stu-id="57829-110">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="57829-111">이 명명 패턴을 따르지 못한 경우 디자이너가 속성을 제대로 보고하지 않을 수 있으며 속성 시스템 스타일 애플리케이션의 특정 측면이 예상대로 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57829-111">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="57829-112">종속성 속성에 대한 기본 메타데이터를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57829-112">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="57829-113">이 예제에서는 `State` 종속성 속성의 기본값이 `false`로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="57829-113">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="57829-114">종속성 속성을 구현 하는 방법과 이유에 대 한 자세한 내용은 전용 필드를 사용 하 여 CLR 속성을 백업 하는 것과는 달리 [종속성 속성 개요](dependency-properties-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57829-114">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57829-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57829-115">See also</span></span>

- [<span data-ttu-id="57829-116">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="57829-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="57829-117">방법 항목</span><span class="sxs-lookup"><span data-stu-id="57829-117">How-to Topics</span></span>](properties-how-to-topics.md)
