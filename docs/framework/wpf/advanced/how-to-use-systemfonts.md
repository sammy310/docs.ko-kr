---
title: '방법: SystemFonts 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 7438705a82faee464649b5f6f577627a379e9a8c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918358"
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="f7a05-102">방법: SystemFonts 사용</span><span class="sxs-lookup"><span data-stu-id="f7a05-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="f7a05-103">이 예제에서는 <xref:System.Windows.SystemFonts> 클래스의 정적 리소스를 사용 하 여 단추에 스타일을 지정 하거나 사용자 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7a05-104">예제</span><span class="sxs-lookup"><span data-stu-id="f7a05-104">Example</span></span>  
 <span data-ttu-id="f7a05-105">시스템 설정과 일관된 시각적 효과를 만들도록 지원하기 위해 시스템 리소스는 몇 가지 시스템이 결정하는 값을 리소스와 속성 모두로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="f7a05-106"><xref:System.Windows.SystemFonts>는 시스템 글꼴 값을 정적 속성으로 포함 하는 클래스이 고, 런타임에 이러한 값에 동적으로 액세스 하는 데 사용할 수 있는 리소스 키를 참조 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="f7a05-107">예 <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 를 들어 <xref:System.Windows.SystemFonts> 은 값이 고 <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 은 해당 리소스 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="f7a05-108">에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 의<xref:System.Windows.SystemFonts> 멤버를 정적 속성 또는 동적 리소스 참조 (정적 속성 값을 키로 사용 하는)로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="f7a05-109">애플리케이션이 실행되는 동안 글꼴 메트릭을 자동으로 업데이트하려면 동적 리소스 참조를 사용하고 자동으로 업데이트하지 않으려면 정적 값 참조를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7a05-110">리소스 키의 경우 속성 이름 뒤에 “Key”라는 접미사가 붙습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="f7a05-111">다음 예제에서는 단추에 스타일을 지정 하거나 사용자 지정 하기 <xref:System.Windows.SystemFonts> 위해의 속성을 정적 값으로 액세스 하 고 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="f7a05-112">이 태그 예제에서는 <xref:System.Windows.SystemFonts> 단추에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="f7a05-113">코드에서의 <xref:System.Windows.SystemFonts> 값을 사용 하려면 정적 값 또는 동적 리소스 참조를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="f7a05-114">대신 <xref:System.Windows.SystemFonts> 클래스의 키가 아닌 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="f7a05-115">키가 아닌 속성이 정적 속성으로 정의 된 경우에도 시스템에서 호스팅되는의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 런타임 동작은 속성을 실시간으로 다시 평가 하 고 시스템 값에 대 한 사용자 기반 변경을 적절 하 게 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="f7a05-116">다음 예제에서는 단추의 글꼴 설정을 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7a05-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="f7a05-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7a05-117">See also</span></span>

- <xref:System.Windows.SystemFonts>
- [<span data-ttu-id="f7a05-118">시스템 브러시로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="f7a05-118">Paint an Area with a System Brush</span></span>](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="f7a05-119">SystemParameters 사용</span><span class="sxs-lookup"><span data-stu-id="f7a05-119">Use SystemParameters</span></span>](how-to-use-systemparameters.md)
- [<span data-ttu-id="f7a05-120">시스템 글꼴 키 사용</span><span class="sxs-lookup"><span data-stu-id="f7a05-120">Use System Fonts Keys</span></span>](how-to-use-system-fonts-keys.md)
- [<span data-ttu-id="f7a05-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f7a05-121">How-to Topics</span></span>](resources-how-to-topics.md)
- [<span data-ttu-id="f7a05-122">x:Static 태그 확장</span><span class="sxs-lookup"><span data-stu-id="f7a05-122">x:Static Markup Extension</span></span>](../../xaml-services/x-static-markup-extension.md)
- [<span data-ttu-id="f7a05-123">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="f7a05-123">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="f7a05-124">DynamicResource 태그 확장</span><span class="sxs-lookup"><span data-stu-id="f7a05-124">DynamicResource Markup Extension</span></span>](dynamicresource-markup-extension.md)
