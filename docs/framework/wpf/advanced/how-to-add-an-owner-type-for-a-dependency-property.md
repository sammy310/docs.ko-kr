---
title: '방법: 종속성 속성에 대한 소유자 형식 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401125"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="69377-102">방법: 종속성 속성에 대한 소유자 형식 추가</span><span class="sxs-lookup"><span data-stu-id="69377-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="69377-103">이 예제에서는 다른 형식에 대해 등록 된 종속성 속성의 소유자로 클래스를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69377-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="69377-104">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이렇게하면판독기와속성시스템이클래스를속성의추가[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 소유자로 인식할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69377-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="69377-105">소유자로 추가 하는 경우 필요에 따라 추가 클래스에서 형식별 메타 데이터를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69377-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="69377-106">다음 예제 `StateProperty` 에서은 `MyStateControl` 클래스에서 등록 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="69377-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="69377-107">클래스 `UnrelatedStateControl` 는 <xref:System.Windows.DependencyProperty.AddOwner%2A> 메서드를 `StateProperty` 사용 하 여 자체를의 소유자로 추가 합니다. 특히, 추가 형식에 있는 종속성 속성에 대 한 새 메타 데이터를 허용 하는 시그니처를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="69377-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="69377-108">속성에 대해 CLR (공용 언어 런타임) 접근자를 제공 하는 것은 [종속성 속성 구현](how-to-implement-a-dependency-property.md) 예제에 표시 된 예제와 비슷하며 소유자로 추가 되는 클래스에 대 한 종속성 속성 식별자를 다시 표시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="69377-108">Notice that you should provide common language runtime (CLR) accessors for the property similar to the example shown in the [Implement a Dependency Property](how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="69377-109">래퍼를 사용 하지 않으면 또는 <xref:System.Windows.DependencyObject.GetValue%2A> <xref:System.Windows.DependencyObject.SetValue%2A>를 사용 하 여 프로그래밍 방식의 액세스 측면에서 종속성 속성을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69377-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="69377-110">그러나 일반적으로 CLR 속성 래퍼를 사용 하 여이 속성 시스템 동작을 병렬 처리 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="69377-110">But you typically want to parallel this property-system behavior with the CLR property wrappers.</span></span> <span data-ttu-id="69377-111">래퍼를 사용 하면 종속성 속성을 프로그래밍 방식으로 쉽게 설정할 수 있으며 속성을 특성으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69377-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="69377-112">기본 메타 데이터를 재정의 하는 방법을 알아보려면 [종속성 속성의 메타 데이터 재정의](how-to-override-metadata-for-a-dependency-property.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69377-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="69377-113">예제</span><span class="sxs-lookup"><span data-stu-id="69377-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="69377-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="69377-114">See also</span></span>

- [<span data-ttu-id="69377-115">사용자 지정 종속성 속성</span><span class="sxs-lookup"><span data-stu-id="69377-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="69377-116">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="69377-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
