---
title: WPF에서 System.Xaml로 마이그레이션된 형식
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 943cdb2a21cbf2f95ef7fe2feefe6c0e71f57be4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939677"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a><span data-ttu-id="85609-102">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="85609-102">Types Migrated from WPF to System.Xaml</span></span>
<span data-ttu-id="85609-103">.NET Framework 3.5 및 .NET Framework 3.0 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 에서 및 Windows Workflow Foundation에는 XAML 언어 구현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-103">In .NET Framework 3.5 and .NET Framework 3.0, both [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] and Windows Workflow Foundation included a XAML language implementation.</span></span> <span data-ttu-id="85609-104">WPF XAML 구현에 대해 확장성을 제공한 공용 형식은 대부분 WindowsBase, PresentationCore 및 PresentationFramework 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-104">Many of the public types that provided extensibility for the WPF XAML implementation existed in the WindowsBase, PresentationCore, and PresentationFramework assemblies.</span></span> <span data-ttu-id="85609-105">마찬가지로 Windows Workflow Foundation XAML에 대해 확장성을 제공한 공용 형식은 System.componentmodel 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-105">Likewise, public types that provided extensibility for Windows Workflow Foundation XAML existed in the System.Workflow.ComponentModel assembly.</span></span> <span data-ttu-id="85609-106">.NET Framework 4에서는 XAML 관련 형식 중 일부가 System.xaml 어셈블리로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-106">In the .NET Framework 4, some of the XAML-related types are migrated to the System.Xaml assembly.</span></span> <span data-ttu-id="85609-107">XAML 언어 서비스의 일반적인 .NET Framework 구현에서는 원래 특정 프레임 워크의 XAML 구현에서 정의 되었지만 이제 전체 .NET Framework 4 XAML 언어 지원의 일부인 많은 XAML 확장성 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-107">A common .NET Framework implementation of XAML language services enables many XAML extensibility scenarios that were originally defined by a specific framework's XAML implementation but are now part of overall .NET Framework 4 XAML language support.</span></span> <span data-ttu-id="85609-108">이 항목에서는 마이그레이션되는 형식을 나열하고 마이그레이션과 관련된 문제를 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-108">This topic lists the types that are migrated and discusses issues related to the migration.</span></span>  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a><span data-ttu-id="85609-109">어셈블리 및 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="85609-109">Assemblies and Namespaces</span></span>  
 <span data-ttu-id="85609-110">.NET Framework 3.5 및 .NET Framework 3.0에서는 XAML을 지원 하기 위해 WPF에서 구현한 형식이 일반적으로 <xref:System.Windows.Markup> 네임 스페이스에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-110">In .NET Framework 3.5 and .NET Framework 3.0, the types that WPF implemented to support XAML were generally in the <xref:System.Windows.Markup> namespace.</span></span> <span data-ttu-id="85609-111">이러한 형식은 대부분 WindowsBase 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-111">Most of these types were in the WindowsBase assembly.</span></span>  
  
 <span data-ttu-id="85609-112">.NET Framework 4에서는 새 <xref:System.Xaml> 네임 스페이스와 새로운 system.xaml 어셈블리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-112">In .NET Framework 4, there is a new <xref:System.Xaml> namespace and a new System.Xaml assembly.</span></span> <span data-ttu-id="85609-113">원래 WPF XAML에 대해 구현된 많은 형식이 이제 XAML 구현에 대한 확장성 지점 또는 서비스로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-113">Many of the types that were originally implemented for WPF XAML are now provided as extensibility points or services for any implementation of XAML.</span></span> <span data-ttu-id="85609-114">보다 일반적인 시나리오에 사용할 수 있도록 하는 작업의 일부로 원래의 WPF 어셈블리에서 System.Xaml 어셈블리로 형식이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-114">As part of making them available for more general scenarios, the types are type-forwarded from their original WPF assembly to the System.Xaml assembly.</span></span> <span data-ttu-id="85609-115">이렇게 하면 다른 프레임 워크 (예: WPF 및 Windows Workflow Foundation)의 어셈블리를 포함 하지 않고 XAML 확장성 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-115">This enables XAML extensibility scenarios without having to include the assemblies of other frameworks (such as WPF and Windows Workflow Foundation).</span></span>  
  
 <span data-ttu-id="85609-116">마이그레이션된 형식의 경우 대부분의 형식이 <xref:System.Windows.Markup> 네임스페이스에 계속 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-116">For migrated types, most of the types remain in the <xref:System.Windows.Markup> namespace.</span></span> <span data-ttu-id="85609-117">이는 부분적으로 기존 구현의 CLR 네임스페이스 매핑이 파일별로 분할되지 않도록 하기 위한 것이었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-117">This was partially to avoid breaking CLR namespace mappings in existing implementations on a per-file basis.</span></span> <span data-ttu-id="85609-118">따라서 .NET Framework 4의 <xref:System.Windows.Markup> 네임 스페이스에는 system.xaml 어셈블리의 일반 XAML 언어 지원 형식과 wpf xaml 구현에 특정 한 형식 (windowsbase 및 기타 WPF 어셈블리에서)이 혼합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-118">As a result, the <xref:System.Windows.Markup> namespace in .NET Framework 4 contains a mixture of general XAML language support types (from the System.Xaml assembly) and types that are specific to the WPF XAML implementation (from WindowsBase and other WPF assemblies).</span></span> <span data-ttu-id="85609-119">System.Xaml로 마이그레이션되었지만 이전에 WPF 어셈블리에 있었던 형식은 WPF 어셈블리의 버전 4에서 형식 전달을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-119">Any type that was migrated to System.Xaml, but existed previously in a WPF assembly, has type-forwarding support in version 4 of the WPF assembly.</span></span>  
  
### <a name="workflow-xaml-support-types"></a><span data-ttu-id="85609-120">워크플로 XAML 지원 형식</span><span class="sxs-lookup"><span data-stu-id="85609-120">Workflow XAML Support Types</span></span>  
 <span data-ttu-id="85609-121">Windows Workflow Foundation는 XAML 지원 형식도 제공 했으며, 대부분의 경우 WPF와 동일한 짧은 이름을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="85609-121">Windows Workflow Foundation also provided XAML support types, and in many cases these had identical short names to a WPF equivalent.</span></span> <span data-ttu-id="85609-122">다음은 Windows Workflow Foundation XAML 지원 형식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="85609-122">The following is a list of Windows Workflow Foundation XAML support types:</span></span>  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 <span data-ttu-id="85609-123">이러한 지원 형식은 .NET Framework 4에 대 한 Windows Workflow Foundation 어셈블리에 계속 존재 하며, 특정 Windows Workflow Foundation 응용 프로그램에 계속 사용할 수 있습니다. 그러나 Windows Workflow Foundation를 사용 하지 않는 응용 프로그램이 나 프레임 워크에서 참조 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-123">These support types still exist in the Windows Workflow Foundation assemblies for .NET Framework 4 and can still be used for specific Windows Workflow Foundation applications; however, they should not be referenced by applications or frameworks that do not use Windows Workflow Foundation.</span></span>  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a><span data-ttu-id="85609-124">MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="85609-124">MarkupExtension</span></span>  
 <span data-ttu-id="85609-125">.NET Framework 3.5 및 .NET Framework 3.0 <xref:System.Windows.Markup.MarkupExtension> 에서는 WPF 용 클래스가 windowsbase 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-125">In the .NET Framework 3.5 and .NET Framework 3.0, the <xref:System.Windows.Markup.MarkupExtension> class for WPF was in the WindowsBase assembly.</span></span> <span data-ttu-id="85609-126">Windows Workflow Foundation <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>에 대 한 병렬 클래스가 system.componentmodel 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-126">A parallel class for Windows Workflow Foundation, <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>, existed in the System.Workflow.ComponentModel assembly.</span></span> <span data-ttu-id="85609-127">.NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> 에서는 클래스가 system.xaml 어셈블리로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-127">In the .NET Framework 4, the <xref:System.Windows.Markup.MarkupExtension> class is migrated to the System.Xaml assembly.</span></span> <span data-ttu-id="85609-128">.NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> 에서는 특정 프레임 워크를 기반으로 하는 .NET Framework 아니라 xaml 서비스를 사용 하는 모든 xaml 확장성 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85609-128">In the .NET Framework 4, <xref:System.Windows.Markup.MarkupExtension> is intended for any XAML extensibility scenario that uses .NET Framework XAML Services, not just for those that build on specific frameworks.</span></span> <span data-ttu-id="85609-129">가능한 경우 특정 프레임워크 또는 프레임워크의 사용자 코드도 XAML 확장에 대한 <xref:System.Windows.Markup.MarkupExtension> 클래스에서 빌드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-129">When possible, specific frameworks or user code in the framework should also build on the <xref:System.Windows.Markup.MarkupExtension> class for XAML extension.</span></span>  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a><span data-ttu-id="85609-130">MarkupExtension 지원 서비스 클래스</span><span class="sxs-lookup"><span data-stu-id="85609-130">MarkupExtension Supporting Service Classes</span></span>  
 <span data-ttu-id="85609-131">.NET Framework 3.5 및 .NET Framework 3.0 for WPF는 <xref:System.Windows.Markup.MarkupExtension> 구현자 및 <xref:System.ComponentModel.TypeConverter> 구현에서 XAML의 형식/속성 사용을 지원 하기 위해 사용할 수 있었던 여러 서비스를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-131">.NET Framework 3.5 and .NET Framework 3.0 for WPF provided several services that were available to <xref:System.Windows.Markup.MarkupExtension> implementers and <xref:System.ComponentModel.TypeConverter> implementations to support type/property usage in XAML.</span></span> <span data-ttu-id="85609-132">이러한 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-132">These services are the following:</span></span>  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
> <span data-ttu-id="85609-133">태그 확장과 관련 된 .NET Framework 3.5의 다른 서비스는 <xref:System.Windows.Markup.IReceiveMarkupExtension> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="85609-133">Another service from .NET Framework 3.5 that is related to markup extensions is the <xref:System.Windows.Markup.IReceiveMarkupExtension> interface.</span></span> <span data-ttu-id="85609-134"><xref:System.Windows.Markup.IReceiveMarkupExtension>마이그레이션되지 않고 .NET Framework 4로 표시 `[Obsolete]` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-134"><xref:System.Windows.Markup.IReceiveMarkupExtension> was not migrated and is marked `[Obsolete]` for .NET Framework 4.</span></span> <span data-ttu-id="85609-135">이전에 <xref:System.Windows.Markup.IReceiveMarkupExtension> 을 사용한 시나리오에서는 대신 <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> 특성 콜백을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-135">Scenarios that previously used <xref:System.Windows.Markup.IReceiveMarkupExtension> should instead use <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> attributed callbacks.</span></span> <span data-ttu-id="85609-136"><xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> 도 `[Obsolete]`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-136"><xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> is also marked `[Obsolete]`.</span></span>  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a><span data-ttu-id="85609-137">XAML 언어 기능</span><span class="sxs-lookup"><span data-stu-id="85609-137">XAML Language Features</span></span>  
 <span data-ttu-id="85609-138">WPF용 여러 XAML 언어 기능과 구성 요소는 이전에 PresentationFramework 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-138">Several XAML language features and components for WPF previously existed in the PresentationFramework assembly.</span></span> <span data-ttu-id="85609-139">이러한 항목은 XAML 태그로 태그 확장 사용을 노출하는 <xref:System.Windows.Markup.MarkupExtension> 서브클래스로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-139">These were implemented as a <xref:System.Windows.Markup.MarkupExtension> subclass to expose markup extension usages in XAML markup.</span></span> <span data-ttu-id="85609-140">.NET Framework 4에서는 WPF 어셈블리를 포함 하지 않는 프로젝트가 이러한 XAML 언어 수준 기능을 사용할 수 있도록 System.xaml 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-140">In .NET Framework 4, these exist in the System.Xaml assembly so that projects that do not include WPF assemblies can use these XAML language-level features.</span></span> <span data-ttu-id="85609-141">WPF는 .NET Framework 4 응용 프로그램에 대해 이와 동일한 구현을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-141">WPF uses these same implementations for .NET Framework 4 applications.</span></span> <span data-ttu-id="85609-142">이 항목에 나열된 다른 경우와 마찬가지로, 지원 형식은 이전 참조가 손상되지 않도록 계속 <xref:System.Windows.Markup> 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-142">As with the other cases that are listed in this topic, the supporting types continue to exist in the <xref:System.Windows.Markup> namespace to avoid breaking previous references.</span></span>  
  
 <span data-ttu-id="85609-143">다음 표에는 System.Xaml에서 정의되는 XAML 기능 지원 클래스 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-143">The following table contains a list of the XAML feature-support classes that are defined in System.Xaml.</span></span>  
  
|<span data-ttu-id="85609-144">XAML 언어 기능</span><span class="sxs-lookup"><span data-stu-id="85609-144">XAML Language Feature</span></span>|<span data-ttu-id="85609-145">사용량</span><span class="sxs-lookup"><span data-stu-id="85609-145">Usage</span></span>|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 <span data-ttu-id="85609-146">System.Xaml에 특정 지원 클래스가 없을 수도 있지만 이제 XAML 언어의 언어 기능 처리를 위한 일반적인 논리가 System.Xaml과 구현된 XAML 판독기 및 XAML 작성기에 상주합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-146">Although System.Xaml may not have specific support classes, the general logic for processing language features for the XAML language now resides in System.Xaml and its implemented XAML readers and XAML writers.</span></span> <span data-ttu-id="85609-147">예를 들어 `x:TypeArguments` 는 System.Xaml 구현의 XAML 판독기 및 XAML 작성기에서 처리되는 특성입니다. XAML 노드 스트림에 기록될 수 있고, 기본(CLR 기반) XAML 스키마 컨텍스트 처리가 있으며, XAML 형식 시스템 표현을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-147">For example, `x:TypeArguments` is an attribute that is processed by XAML readers and XAML writers from System.Xaml implementations; it can be noted in the XAML node stream, has handling in the default (CLR-based) XAML schema context, has a XAML type-system representation, and so on.</span></span> <span data-ttu-id="85609-148">결과적으로, 모든 XAML 언어 수준 기능에 대한 참조 설명서는 3.5 설명서 집합에서와 같이 [고급(Windows Presentation Foundation)](index.md) 의 하위 항목으로 WPF 설명서에 포함되는 대신 [XAML Services](../wpf/advanced/index.md) 의 하위 항목 및 .NET Framework 설명서 집합의 일반 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="85609-148">As a result, the reference documentation for all XAML language-level features is a subtopic for [XAML Services](index.md) and that general area of the .NET Framework documentation set, instead of being part of the WPF documentation set as a subtopic of [Advanced (Windows Presentation Foundation)](../wpf/advanced/index.md) (as is still the case in 3.5 documentation sets).</span></span>  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a><span data-ttu-id="85609-149">ValueSerializer 및 지원 클래스</span><span class="sxs-lookup"><span data-stu-id="85609-149">ValueSerializer and Supporting Classes</span></span>  
 <span data-ttu-id="85609-150"><xref:System.Windows.Markup.ValueSerializer> 클래스는 특히 직렬화 시 출력에 여러 모드 또는 노드가 필요할 수 있는 XAML 직렬화 사례를 위해 문자열로의 형식 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-150">The <xref:System.Windows.Markup.ValueSerializer> class supports type conversion to a string, particularly for XAML serialization cases where serialization may require multiple modes or nodes in the output.</span></span> <span data-ttu-id="85609-151">.NET Framework 3.5 및 .NET Framework 3.0 <xref:System.Windows.Markup.ValueSerializer> 에서는 WPF 용가 windowsbase 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-151">In .NET Framework 3.5 and .NET Framework 3.0, the <xref:System.Windows.Markup.ValueSerializer> for WPF was in the WindowsBase assembly.</span></span> <span data-ttu-id="85609-152">.NET Framework 4에서 클래스는 <xref:System.Windows.Markup.ValueSerializer> system.xaml에 있으며 WPF에서 빌드하는 시나리오 뿐만 아니라 모든 Xaml 확장성 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85609-152">In the .NET Framework 4, the <xref:System.Windows.Markup.ValueSerializer> class is in System.Xaml and is intended for any XAML extensibility scenario, not just for those that build on WPF.</span></span> <span data-ttu-id="85609-153"><xref:System.Windows.Markup.IValueSerializerContext> (지원 서비스) 및 <xref:System.Windows.Markup.DateTimeValueSerializer> (특정 서브클래스)도 System.Xaml로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-153"><xref:System.Windows.Markup.IValueSerializerContext> (a supporting service) and <xref:System.Windows.Markup.DateTimeValueSerializer> (a specific subclass) are also migrated to System.Xaml.</span></span>  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a><span data-ttu-id="85609-154">XAML 관련 특성</span><span class="sxs-lookup"><span data-stu-id="85609-154">XAML-Related Attributes</span></span>  
 <span data-ttu-id="85609-155">WPF XAML은 XAML 동작에 대한 특징을 나타내기 위해 CLR 형식에 적용할 수 있는 여러 특성을 포함했습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-155">WPF XAML included several attributes that can be applied to CLR types to indicate something about their XAML behavior.</span></span> <span data-ttu-id="85609-156">다음은 .NET Framework 3.5 및 .NET Framework 3.0에서 WPF 어셈블리에 있었던 특성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="85609-156">The following is a list of the attributes that existed in WPF assemblies in .NET Framework 3.5 and .NET Framework 3.0.</span></span> <span data-ttu-id="85609-157">이러한 특성은 .NET Framework 4에서 System.xaml로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-157">These attributes are migrated to System.Xaml in .NET Framework 4.</span></span>  
  
- <xref:System.Windows.Markup.AmbientAttribute>  
  
- <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
- <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
- <xref:System.Windows.Markup.DependsOnAttribute>  
  
- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
- <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
- <xref:System.Windows.Markup.RootNamespaceAttribute>  
  
- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
- <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
- <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
- <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a><span data-ttu-id="85609-158">기타 클래스</span><span class="sxs-lookup"><span data-stu-id="85609-158">Miscellaneous Classes</span></span>  
 <span data-ttu-id="85609-159">인터페이스 <xref:System.Windows.Markup.IComponentConnector> 는 .NET Framework 3.5 및 .NET Framework 3.0의 windowsbase에 있었지만 .NET Framework 4의 system.xaml에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-159">The <xref:System.Windows.Markup.IComponentConnector> interface existed in WindowsBase in the .NET Framework 3.5 and .NET Framework 3.0, but exists in System.Xaml in .NET Framework 4.</span></span> <span data-ttu-id="85609-160"><xref:System.Windows.Markup.IComponentConnector> 는 주로 도구 지원 및 XAML 태그 컴파일러에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85609-160"><xref:System.Windows.Markup.IComponentConnector> is primarily intended for tooling support and XAML markup compilers.</span></span>  
  
 <span data-ttu-id="85609-161">인터페이스 <xref:System.Windows.Markup.INameScope> 는 .NET Framework 3.5 및 .NET Framework 3.0의 windowsbase에 있었지만 .NET Framework 4의 system.xaml에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-161">The <xref:System.Windows.Markup.INameScope> interface existed in WindowsBase in the .NET Framework 3.5 and .NET Framework 3.0, but exists in System.Xaml in .NET Framework 4.</span></span> <span data-ttu-id="85609-162"><xref:System.Windows.Markup.INameScope> 는 XAML 네임스페이스에 대한 기본 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-162"><xref:System.Windows.Markup.INameScope> defines basic operations for a XAML namescope.</span></span>  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a><span data-ttu-id="85609-163">WPF 및 System.Xaml에 있는 공유 이름의 XAML 관련 클래스</span><span class="sxs-lookup"><span data-stu-id="85609-163">XAML-related Classes with Shared Names that Exist in WPF and System.Xaml</span></span>  
 <span data-ttu-id="85609-164">다음 클래스는 .NET Framework 4에서 WPF 어셈블리와 System.xaml 어셈블리 둘 다에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-164">The following classes exist in both the WPF assemblies and the System.Xaml assembly in the .NET Framework 4:</span></span>  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 <span data-ttu-id="85609-165">WPF 구현은 <xref:System.Windows.Markup> 네임스페이스 및 PresentationFramework 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-165">The WPF implementation is found in the <xref:System.Windows.Markup> namespace, and PresentationFramework assembly.</span></span> <span data-ttu-id="85609-166">System.Xaml 구현은 <xref:System.Xaml> 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-166">The System.Xaml implementation is found in the <xref:System.Xaml> namespace.</span></span> <span data-ttu-id="85609-167">WPF 형식을 사용하거나 WPF 형식에서 파생하는 경우 일반적으로 System.Xaml 구현 대신 <xref:System.Windows.Markup.XamlReader> 및 <xref:System.Windows.Markup.XamlWriter> 의 WPF 구현을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85609-167">If you are using WPF types or are deriving from WPF types, you should typically use the WPF implementations of <xref:System.Windows.Markup.XamlReader> and <xref:System.Windows.Markup.XamlWriter> instead of the System.Xaml implementations.</span></span> <span data-ttu-id="85609-168">자세한 내용은 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 및 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>의 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85609-168">For more information, see Remarks in <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="85609-169">WPF 어셈블리 및 System.Xaml에 대한 참조를 둘 다 포함하고 `include` 및 <xref:System.Windows.Markup> 네임스페이스에 모두 <xref:System.Xaml> 문을 사용하는 경우 형식을 명확하게 확인하기 위해 이러한 API에 대한 호출을 정규화해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85609-169">If you are including references to both WPF assemblies and System.Xaml, and you also are using `include` statements for both the <xref:System.Windows.Markup> and <xref:System.Xaml> namespaces, you may need to fully qualify the calls to these APIs in order to resolve the types without ambiguity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85609-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="85609-170">See also</span></span>

- [<span data-ttu-id="85609-171">XAML 서비스</span><span class="sxs-lookup"><span data-stu-id="85609-171">XAML Services</span></span>](index.md)
