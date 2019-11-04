---
title: '방법: 리소스 정의 및 참조'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 89471c45aabd9f3415c45a2e8af41d1a52900324
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460179"
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="784af-102">방법: 리소스 정의 및 참조</span><span class="sxs-lookup"><span data-stu-id="784af-102">How to: Define and Reference a Resource</span></span>

<span data-ttu-id="784af-103">이 예제에서는 리소스를 정의 하 고 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 특성을 사용 하 여 참조 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="784af-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

## <a name="example"></a><span data-ttu-id="784af-104">예제</span><span class="sxs-lookup"><span data-stu-id="784af-104">Example</span></span>

<span data-ttu-id="784af-105">다음 예제에서는 두 가지 리소스 유형인 <xref:System.Windows.Media.SolidColorBrush> 리소스 및 여러 <xref:System.Windows.Style> 리소스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="784af-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="784af-106"><xref:System.Windows.Media.SolidColorBrush> 리소스 `MyBrush`는 각각 <xref:System.Windows.Media.Brush> 형식 값을 사용 하는 여러 속성의 값을 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="784af-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="784af-107"><xref:System.Windows.Style> 리소스는 각 대상에 특정 컨트롤 형식을 `PageBackground``TitleText` 하 고 `Label` 합니다.</span><span class="sxs-lookup"><span data-stu-id="784af-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="784af-108">스타일은 리소스 키에서 해당 스타일 리소스를 참조 하 고 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의 된 여러 특정 컨트롤 요소의 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 설정 하는 데 사용 되는 경우 대상 컨트롤에 다양 한 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="784af-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>

<span data-ttu-id="784af-109">`Label` 스타일의 setter에 있는 속성 중 하나가 앞에서 정의한 `MyBrush` 리소스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="784af-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="784af-110">이는 일반적인 방법 이지만 리소스를 구문 분석 하 여 지정 된 순서 대로 리소스 사전에 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="784af-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="784af-111">[StaticResource 태그 확장](staticresource-markup-extension.md) 을 사용 하 여 다른 리소스 내에서 참조 하는 경우에도 리소스는 사전에 있는 순서에 의해 요청 됩니다.</span><span class="sxs-lookup"><span data-stu-id="784af-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="784af-112">참조 하는 리소스는 리소스 컬렉션 내에서 리소스를 요청 하는 위치 보다 앞서 정의 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="784af-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="784af-113">필요한 경우 런타임에 리소스를 참조 하는 [DynamicResource 태그 확장](dynamicresource-markup-extension.md) 을 사용 하 여 리소스 참조의 엄격한 생성 순서를 해결할 수 있지만이 DynamicResource 기술에는 성능이 있습니다. 미치는.</span><span class="sxs-lookup"><span data-stu-id="784af-113">If necessary, you can work around the strict creation order of resource references by using a [DynamicResource Markup Extension](dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="784af-114">자세한 내용은 [XAML 리소스](xaml-resources.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="784af-114">For details, see [XAML Resources](xaml-resources.md).</span></span>

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a><span data-ttu-id="784af-115">참조</span><span class="sxs-lookup"><span data-stu-id="784af-115">See also</span></span>

- [<span data-ttu-id="784af-116">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="784af-116">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="784af-117">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="784af-117">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
