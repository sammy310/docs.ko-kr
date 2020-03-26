---
title: WPF에서 System.Xaml로 마이그레이션된 형식
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 5aa2d8a39be47d9affb97c3b60e53c4722c63cce
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249815"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a><span data-ttu-id="d65c6-102">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="d65c6-102">Types migrated from WPF to System.Xaml</span></span>

<span data-ttu-id="d65c6-103">.NET Framework 3.5 및 .NET Framework 3.0에서는 WPF(Windows 프레젠테이션 파운데이션)와 Windows 워크플로 우대 재단에 XAML 언어 구현이 모두 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-103">In .NET Framework 3.5 and .NET Framework 3.0, both Windows Presentation Foundation (WPF) and Windows Workflow Foundation included a XAML language implementation.</span></span> <span data-ttu-id="d65c6-104">WPF XAML 구현에 대해 확장성을 제공한 공용 형식은 대부분 WindowsBase, PresentationCore 및 PresentationFramework 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-104">Many of the public types that provided extensibility for the WPF XAML implementation existed in the WindowsBase, PresentationCore, and PresentationFramework assemblies.</span></span> <span data-ttu-id="d65c6-105">마찬가지로 Windows 워크플로 파운데이션 XAML에 대한 확장성을 제공하는 공용 형식은 System.Workflow.ComponentModel 어셈블리에 존재했습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-105">Likewise, public types that provided extensibility for Windows Workflow Foundation XAML existed in the System.Workflow.ComponentModel assembly.</span></span> <span data-ttu-id="d65c6-106">.NET 프레임워크 4에서 일부 XAML 관련 형식이 System.Xaml 어셈블리로 마이그레이션되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-106">In the .NET Framework 4, some of the XAML-related types were migrated to the System.Xaml assembly.</span></span> <span data-ttu-id="d65c6-107">XAML 언어 서비스의 일반적인 .NET Framework 구현을 사용하면 원래 특정 프레임워크의 XAML 구현에 의해 정의되었지만 이제는 전체 .NET Framework 4 XAML 언어 지원의 일부인 많은 XAML 확장성 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-107">A common .NET Framework implementation of XAML language services enables many XAML extensibility scenarios that were originally defined by a specific framework's XAML implementation but are now part of overall .NET Framework 4 XAML language support.</span></span> <span data-ttu-id="d65c6-108">이 문서에서는 마이그레이션된 형식을 나열하고 마이그레이션과 관련된 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-108">This article lists the types that were migrated and discusses issues related to the migration.</span></span>

## <a name="assemblies-and-namespaces"></a><span data-ttu-id="d65c6-109">어셈블리 및 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="d65c6-109">Assemblies and Namespaces</span></span>

<span data-ttu-id="d65c6-110">.NET Framework 3.5 및 .NET Framework 3.0에서 XAML을 지원하기 위해 <xref:System.Windows.Markup> WPF가 구현한 형식은 일반적으로 네임스페이스에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-110">In .NET Framework 3.5 and .NET Framework 3.0, the types that WPF implemented to support XAML were generally in the <xref:System.Windows.Markup> namespace.</span></span> <span data-ttu-id="d65c6-111">이러한 형식은 대부분 WindowsBase 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-111">Most of these types were in the WindowsBase assembly.</span></span>

<span data-ttu-id="d65c6-112">.NET 프레임워크 4에는 새 <xref:System.Xaml> 네임스페이스와 새 System.Xaml 어셈블리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-112">In .NET Framework 4, there is a new <xref:System.Xaml> namespace and a new System.Xaml assembly.</span></span> <span data-ttu-id="d65c6-113">원래 WPF XAML에 대해 구현된 많은 형식이 이제 XAML 구현에 대한 확장성 지점 또는 서비스로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-113">Many of the types that were originally implemented for WPF XAML are now provided as extensibility points or services for any implementation of XAML.</span></span> <span data-ttu-id="d65c6-114">보다 일반적인 시나리오에 사용할 수 있도록 하는 작업의 일부로 원래의 WPF 어셈블리에서 System.Xaml 어셈블리로 형식이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-114">As part of making them available for more general scenarios, the types are type-forwarded from their original WPF assembly to the System.Xaml assembly.</span></span> <span data-ttu-id="d65c6-115">이렇게 하면 다른 프레임워크(예: WPF 및 Windows 워크플로 재단)의 어셈블리를 포함하지 않고도 XAML 확장성 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-115">This enables XAML extensibility scenarios without having to include the assemblies of other frameworks (such as WPF and Windows Workflow Foundation).</span></span>

<span data-ttu-id="d65c6-116">마이그레이션된 형식의 경우 대부분의 형식이 <xref:System.Windows.Markup> 네임스페이스에 계속 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-116">For migrated types, most of the types remain in the <xref:System.Windows.Markup> namespace.</span></span> <span data-ttu-id="d65c6-117">이는 부분적으로 기존 구현의 CLR 네임스페이스 매핑이 파일별로 분할되지 않도록 하기 위한 것이었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-117">This was partially to avoid breaking CLR namespace mappings in existing implementations on a per-file basis.</span></span> <span data-ttu-id="d65c6-118">따라서 .NET <xref:System.Windows.Markup> Framework 4의 네임스페이스에는 일반 XAML 언어 지원 형식(System.Xaml 어셈블리)과 WPF XAML 구현(WindowsBase 및 기타 WPF 어셈블리)과 관련된 형식이 혼합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-118">As a result, the <xref:System.Windows.Markup> namespace in .NET Framework 4 contains a mixture of general XAML language support types (from the System.Xaml assembly) and types that are specific to the WPF XAML implementation (from WindowsBase and other WPF assemblies).</span></span> <span data-ttu-id="d65c6-119">System.Xaml로 마이그레이션되었지만 이전에 WPF 어셈블리에 있었던 형식은 WPF 어셈블리의 버전 4에서 형식 전달을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-119">Any type that was migrated to System.Xaml, but existed previously in a WPF assembly, has type-forwarding support in version 4 of the WPF assembly.</span></span>

### <a name="workflow-xaml-support-types"></a><span data-ttu-id="d65c6-120">워크플로 XAML 지원 형식</span><span class="sxs-lookup"><span data-stu-id="d65c6-120">Workflow XAML Support Types</span></span>

<span data-ttu-id="d65c6-121">또한 Windows 워크플로 우로 재단은 XAML 지원 유형을 제공했으며 대부분의 경우 이러한 이름은 WPF와 동일한 짧은 이름을 가지고 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-121">Windows Workflow Foundation also provided XAML support types, and in many cases these had identical short names to a WPF equivalent.</span></span> <span data-ttu-id="d65c6-122">다음은 Windows 워크플로 기반 XAML 지원 유형 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-122">The following is a list of Windows Workflow Foundation XAML support types:</span></span>

- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>

<span data-ttu-id="d65c6-123">이러한 지원 유형은 .NET Framework 4용 Windows 워크플로 파운데이션 어셈블리에 여전히 존재하며 특정 Windows 워크플로 파운데이션 응용 프로그램에 계속 사용할 수 있습니다. 그러나 Windows 워크플로 파운데이션을 사용하지 않는 응용 프로그램이나 프레임워크에서 참조해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-123">These support types still exist in the Windows Workflow Foundation assemblies for .NET Framework 4 and can still be used for specific Windows Workflow Foundation applications; however, they should not be referenced by applications or frameworks that do not use Windows Workflow Foundation.</span></span>

## <a name="markupextension"></a><span data-ttu-id="d65c6-124">MarkupExtension</span><span class="sxs-lookup"><span data-stu-id="d65c6-124">MarkupExtension</span></span>

<span data-ttu-id="d65c6-125">.NET 프레임워크 3.5 및 .NET Framework 3.0에서 WPF에 대한 <xref:System.Windows.Markup.MarkupExtension> 클래스는 WindowsBase 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-125">In the .NET Framework 3.5 and .NET Framework 3.0, the <xref:System.Windows.Markup.MarkupExtension> class for WPF was in the WindowsBase assembly.</span></span> <span data-ttu-id="d65c6-126">Windows 워크플로 파운데이션에 <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>대한 병렬 클래스는 System.Workflow.ComponentModel 어셈블리에 존재했습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-126">A parallel class for Windows Workflow Foundation, <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>, existed in the System.Workflow.ComponentModel assembly.</span></span> <span data-ttu-id="d65c6-127">.NET 프레임워크 4에서 <xref:System.Windows.Markup.MarkupExtension> 클래스는 System.Xaml 어셈블리로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-127">In the .NET Framework 4, the <xref:System.Windows.Markup.MarkupExtension> class is migrated to the System.Xaml assembly.</span></span> <span data-ttu-id="d65c6-128">.NET Framework 4에서는 <xref:System.Windows.Markup.MarkupExtension> 특정 프레임워크를 기반으로 하는 XAML 서비스뿐만 아니라 .NET XAML 서비스를 사용하는 모든 XAML 확장성 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-128">In the .NET Framework 4, <xref:System.Windows.Markup.MarkupExtension> is intended for any XAML extensibility scenario that uses .NET XAML Services, not just for those that build on specific frameworks.</span></span> <span data-ttu-id="d65c6-129">가능한 경우 특정 프레임워크 또는 프레임워크의 사용자 코드도 XAML 확장에 대한 <xref:System.Windows.Markup.MarkupExtension> 클래스에서 빌드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-129">When possible, specific frameworks or user code in the framework should also build on the <xref:System.Windows.Markup.MarkupExtension> class for XAML extension.</span></span>

## <a name="markupextension-supporting-service-classes"></a><span data-ttu-id="d65c6-130">MarkupExtension 지원 서비스 클래스</span><span class="sxs-lookup"><span data-stu-id="d65c6-130">MarkupExtension Supporting Service Classes</span></span>

<span data-ttu-id="d65c6-131">WPF용 .NET Framework 3.5 및 .NET Framework 3.0은 XAML에서 형식/속성 사용을 지원하기 위해 <xref:System.Windows.Markup.MarkupExtension> 구현자와 <xref:System.ComponentModel.TypeConverter> 구현에 사용할 수 있는 여러 서비스를 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-131">.NET Framework 3.5 and .NET Framework 3.0 for WPF provided several services that were available to <xref:System.Windows.Markup.MarkupExtension> implementers and <xref:System.ComponentModel.TypeConverter> implementations to support type/property usage in XAML.</span></span> <span data-ttu-id="d65c6-132">이러한 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-132">These services are the following:</span></span>

- <xref:System.Windows.Markup.IProvideValueTarget>

- <xref:System.Windows.Markup.IUriContext>

- <xref:System.Windows.Markup.IXamlTypeResolver>

> [!NOTE]
> <span data-ttu-id="d65c6-133">.NET Framework 3.5의 태그 확장과 관련된 또 <xref:System.Windows.Markup.IReceiveMarkupExtension> 다른 서비스는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-133">Another service from .NET Framework 3.5 that is related to markup extensions is the <xref:System.Windows.Markup.IReceiveMarkupExtension> interface.</span></span> <span data-ttu-id="d65c6-134"><xref:System.Windows.Markup.IReceiveMarkupExtension>마이그레이션되지 않았으며 .NET `[Obsolete]` Framework 4로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-134"><xref:System.Windows.Markup.IReceiveMarkupExtension> was not migrated and is marked `[Obsolete]` for .NET Framework 4.</span></span> <span data-ttu-id="d65c6-135">이전에 <xref:System.Windows.Markup.IReceiveMarkupExtension> 을 사용한 시나리오에서는 대신 <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> 특성 콜백을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-135">Scenarios that previously used <xref:System.Windows.Markup.IReceiveMarkupExtension> should instead use <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> attributed callbacks.</span></span> <span data-ttu-id="d65c6-136"><xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> 도 `[Obsolete]`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-136"><xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> is also marked `[Obsolete]`.</span></span>

## <a name="xaml-language-features"></a><span data-ttu-id="d65c6-137">XAML 언어 기능</span><span class="sxs-lookup"><span data-stu-id="d65c6-137">XAML Language Features</span></span>

<span data-ttu-id="d65c6-138">WPF용 여러 XAML 언어 기능과 구성 요소는 이전에 PresentationFramework 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-138">Several XAML language features and components for WPF previously existed in the PresentationFramework assembly.</span></span> <span data-ttu-id="d65c6-139">이러한 항목은 XAML 태그로 태그 확장 사용을 노출하는 <xref:System.Windows.Markup.MarkupExtension> 서브클래스로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-139">These were implemented as a <xref:System.Windows.Markup.MarkupExtension> subclass to expose markup extension usages in XAML markup.</span></span> <span data-ttu-id="d65c6-140">.NET Framework 4에서는 WPF 어셈블리를 포함하지 않는 프로젝트가 이러한 XAML 언어 수준 기능을 사용할 수 있도록 System.Xaml 어셈블리에 이러한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-140">In .NET Framework 4, these exist in the System.Xaml assembly so that projects that do not include WPF assemblies can use these XAML language-level features.</span></span> <span data-ttu-id="d65c6-141">WPF는 .NET Framework 4 응용 프로그램에 대해 동일한 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-141">WPF uses these same implementations for .NET Framework 4 applications.</span></span> <span data-ttu-id="d65c6-142">이 항목에 나열된 다른 경우와 마찬가지로, 지원 형식은 이전 참조가 손상되지 않도록 계속 <xref:System.Windows.Markup> 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-142">As with the other cases that are listed in this topic, the supporting types continue to exist in the <xref:System.Windows.Markup> namespace to avoid breaking previous references.</span></span>

<span data-ttu-id="d65c6-143">다음 표에는 System.Xaml에서 정의되는 XAML 기능 지원 클래스 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-143">The following table contains a list of the XAML feature-support classes that are defined in System.Xaml.</span></span>

|<span data-ttu-id="d65c6-144">XAML 언어 기능</span><span class="sxs-lookup"><span data-stu-id="d65c6-144">XAML Language Feature</span></span>|<span data-ttu-id="d65c6-145">사용</span><span class="sxs-lookup"><span data-stu-id="d65c6-145">Usage</span></span>|
|---------------------------|-----------|
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|

<span data-ttu-id="d65c6-146">System.Xaml에 특정 지원 클래스가 없을 수도 있지만 이제 XAML 언어의 언어 기능 처리를 위한 일반적인 논리가 System.Xaml과 구현된 XAML 판독기 및 XAML 작성기에 상주합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-146">Although System.Xaml may not have specific support classes, the general logic for processing language features for the XAML language now resides in System.Xaml and its implemented XAML readers and XAML writers.</span></span> <span data-ttu-id="d65c6-147">예를 들어 `x:TypeArguments` 는 System.Xaml 구현의 XAML 판독기 및 XAML 작성기에서 처리되는 특성입니다. XAML 노드 스트림에 기록될 수 있고, 기본(CLR 기반) XAML 스키마 컨텍스트 처리가 있으며, XAML 형식 시스템 표현을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-147">For example, `x:TypeArguments` is an attribute that is processed by XAML readers and XAML writers from System.Xaml implementations; it can be noted in the XAML node stream, has handling in the default (CLR-based) XAML schema context, has a XAML type-system representation, and so on.</span></span> <span data-ttu-id="d65c6-148">따라서 모든 XAML 언어 수준 기능에 대한 참조 설명서는 [WPF(Windows 프레젠테이션 기반)에 대한 데스크톱 가이드의](../../../desktop-wpf/overview/index.md) [XAML 서비스에](../../../desktop-wpf/xaml-services/index.md) 대한 하위 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-148">As a result, the reference documentation for all XAML language-level features is a subtopic for [XAML Services](../../../desktop-wpf/xaml-services/index.md) in the [Desktop Guide for Windows Presentation Foundation (WPF)](../../../desktop-wpf/overview/index.md).</span></span>

## <a name="valueserializer-and-supporting-classes"></a><span data-ttu-id="d65c6-149">ValueSerializer 및 지원 클래스</span><span class="sxs-lookup"><span data-stu-id="d65c6-149">ValueSerializer and Supporting Classes</span></span>

<span data-ttu-id="d65c6-150"><xref:System.Windows.Markup.ValueSerializer> 클래스는 특히 직렬화 시 출력에 여러 모드 또는 노드가 필요할 수 있는 XAML 직렬화 사례를 위해 문자열로의 형식 변환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-150">The <xref:System.Windows.Markup.ValueSerializer> class supports type conversion to a string, particularly for XAML serialization cases where serialization may require multiple modes or nodes in the output.</span></span> <span data-ttu-id="d65c6-151">.NET 프레임워크 3.5 및 .NET 프레임워크 <xref:System.Windows.Markup.ValueSerializer> 3.0에서 WPF용은 WindowsBase 어셈블리에 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-151">In .NET Framework 3.5 and .NET Framework 3.0, the <xref:System.Windows.Markup.ValueSerializer> for WPF was in the WindowsBase assembly.</span></span> <span data-ttu-id="d65c6-152">.NET Framework 4에서 <xref:System.Windows.Markup.ValueSerializer> 클래스는 System.Xaml에 있으며 WPF에서 빌드하는 XAML 확장성 시나리오뿐만 아니라 모든 XAML 확장성 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-152">In the .NET Framework 4, the <xref:System.Windows.Markup.ValueSerializer> class is in System.Xaml and is intended for any XAML extensibility scenario, not just for those that build on WPF.</span></span> <span data-ttu-id="d65c6-153"><xref:System.Windows.Markup.IValueSerializerContext> (지원 서비스) 및 <xref:System.Windows.Markup.DateTimeValueSerializer> (특정 서브클래스)도 System.Xaml로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-153"><xref:System.Windows.Markup.IValueSerializerContext> (a supporting service) and <xref:System.Windows.Markup.DateTimeValueSerializer> (a specific subclass) are also migrated to System.Xaml.</span></span>

## <a name="xaml-related-attributes"></a><span data-ttu-id="d65c6-154">XAML 관련 특성</span><span class="sxs-lookup"><span data-stu-id="d65c6-154">XAML-Related Attributes</span></span>

<span data-ttu-id="d65c6-155">WPF XAML은 XAML 동작에 대한 특징을 나타내기 위해 CLR 형식에 적용할 수 있는 여러 특성을 포함했습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-155">WPF XAML included several attributes that can be applied to CLR types to indicate something about their XAML behavior.</span></span> <span data-ttu-id="d65c6-156">다음은 .NET Framework 3.5 및 .NET Framework 3.0의 WPF 어셈블리에 있는 특성 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-156">The following is a list of the attributes that existed in WPF assemblies in .NET Framework 3.5 and .NET Framework 3.0.</span></span> <span data-ttu-id="d65c6-157">이러한 특성은 .NET 프레임워크 4의 System.Xaml로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-157">These attributes are migrated to System.Xaml in .NET Framework 4.</span></span>

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

## <a name="miscellaneous-classes"></a><span data-ttu-id="d65c6-158">기타 클래스</span><span class="sxs-lookup"><span data-stu-id="d65c6-158">Miscellaneous Classes</span></span>

<span data-ttu-id="d65c6-159">인터페이스는 <xref:System.Windows.Markup.IComponentConnector> .NET Framework 3.5 및 .NET Framework 3.0의 WindowsBase에 존재하지만 .NET 프레임워크 4의 System.Xaml에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-159">The <xref:System.Windows.Markup.IComponentConnector> interface existed in WindowsBase in .NET Framework 3.5 and .NET Framework 3.0, but exists in System.Xaml in .NET Framework 4.</span></span> <span data-ttu-id="d65c6-160"><xref:System.Windows.Markup.IComponentConnector> 는 주로 도구 지원 및 XAML 태그 컴파일러에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-160"><xref:System.Windows.Markup.IComponentConnector> is primarily intended for tooling support and XAML markup compilers.</span></span>

<span data-ttu-id="d65c6-161">인터페이스는 <xref:System.Windows.Markup.INameScope> .NET Framework 3.5 및 .NET Framework 3.0의 WindowsBase에 존재하지만 .NET 프레임워크 4의 System.Xaml에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-161">The <xref:System.Windows.Markup.INameScope> interface existed in WindowsBase in .NET Framework 3.5 and .NET Framework 3.0, but exists in System.Xaml in .NET Framework 4.</span></span> <span data-ttu-id="d65c6-162"><xref:System.Windows.Markup.INameScope> 는 XAML 네임스페이스에 대한 기본 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-162"><xref:System.Windows.Markup.INameScope> defines basic operations for a XAML namescope.</span></span>

## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a><span data-ttu-id="d65c6-163">WPF 및 System.Xaml에 있는 공유 이름의 XAML 관련 클래스</span><span class="sxs-lookup"><span data-stu-id="d65c6-163">XAML-related Classes with Shared Names that Exist in WPF and System.Xaml</span></span>

<span data-ttu-id="d65c6-164">다음 클래스는 .NET 프레임워크 4의 WPF 어셈블리와 System.Xaml 어셈블리 모두에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-164">The following classes exist in both the WPF assemblies and the System.Xaml assembly in .NET Framework 4:</span></span>

`XamlReader`

`XamlWriter`

`XamlParseException`

<span data-ttu-id="d65c6-165">WPF 구현은 <xref:System.Windows.Markup> 네임스페이스 및 PresentationFramework 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-165">The WPF implementation is found in the <xref:System.Windows.Markup> namespace, and PresentationFramework assembly.</span></span> <span data-ttu-id="d65c6-166">System.Xaml 구현은 <xref:System.Xaml> 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-166">The System.Xaml implementation is found in the <xref:System.Xaml> namespace.</span></span> <span data-ttu-id="d65c6-167">WPF 형식을 사용하거나 WPF 형식에서 파생하는 경우 일반적으로 System.Xaml 구현 대신 <xref:System.Windows.Markup.XamlReader> 및 <xref:System.Windows.Markup.XamlWriter> 의 WPF 구현을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-167">If you are using WPF types or are deriving from WPF types, you should typically use the WPF implementations of <xref:System.Windows.Markup.XamlReader> and <xref:System.Windows.Markup.XamlWriter> instead of the System.Xaml implementations.</span></span> <span data-ttu-id="d65c6-168">자세한 내용은 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 및 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>의 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d65c6-168">For more information, see Remarks in <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> and <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d65c6-169">WPF 어셈블리 및 System.Xaml에 대한 참조를 둘 다 포함하고 `include` 및 <xref:System.Windows.Markup> 네임스페이스에 모두 <xref:System.Xaml> 문을 사용하는 경우 형식을 명확하게 확인하기 위해 이러한 API에 대한 호출을 정규화해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d65c6-169">If you are including references to both WPF assemblies and System.Xaml, and you also are using `include` statements for both the <xref:System.Windows.Markup> and <xref:System.Xaml> namespaces, you may need to fully qualify the calls to these APIs in order to resolve the types without ambiguity.</span></span>
