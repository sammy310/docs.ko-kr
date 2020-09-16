---
title: x:Static 태그 확장
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: 634a480b4d7446ed09708f6c91276d1c2f61d4a9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551613"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="8a292-102">x:Static 태그 확장</span><span class="sxs-lookup"><span data-stu-id="8a292-102">x:Static Markup Extension</span></span>

<span data-ttu-id="8a292-103">CLS (공용 언어 사양) 규격 방식으로 정의 된 모든 정적 값으로 된 코드 엔터티를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="8a292-104">참조 되는 정적 속성은 XAML에서 속성의 값을 제공 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="8a292-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="8a292-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="8a292-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="8a292-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="8a292-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-107">Optional.</span></span> <span data-ttu-id="8a292-108">기본이 아닌 매핑된 XAML 네임 스페이스를 참조 하는 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="8a292-109">`prefix` 은 기본 XAML 네임 스페이스에서 제공 되는 정적 속성을 거의 참조 하지 않으므로 사용 시 명시적으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="8a292-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a292-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="8a292-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8a292-111">Required.</span></span> <span data-ttu-id="8a292-112">원하는 정적 멤버를 정의 하는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="8a292-113">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8a292-113">Required.</span></span> <span data-ttu-id="8a292-114">원하는 정적 값 멤버의 이름 (상수, 정적 속성, 필드 또는 열거형 값)입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="8a292-115">설명</span><span class="sxs-lookup"><span data-stu-id="8a292-115">Remarks</span></span>

<span data-ttu-id="8a292-116">참조 되는 코드 엔터티는 다음 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="8a292-117">상수</span><span class="sxs-lookup"><span data-stu-id="8a292-117">A constant</span></span>
- <span data-ttu-id="8a292-118">정적 속성</span><span class="sxs-lookup"><span data-stu-id="8a292-118">A static property</span></span>
- <span data-ttu-id="8a292-119">필드</span><span class="sxs-lookup"><span data-stu-id="8a292-119">A field</span></span>
- <span data-ttu-id="8a292-120">열거형 값</span><span class="sxs-lookup"><span data-stu-id="8a292-120">An enumeration value</span></span>

<span data-ttu-id="8a292-121">비정적 속성과 같은 다른 코드 엔터티를 지정 하면 XAML이 태그 컴파일 인 경우 컴파일 시간 오류가 발생 하거나 XAML 로드 시간 구문 분석 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="8a292-122">`x:Static`현재 xaml 문서에 대 한 기본 xaml 네임 스페이스에 없는 정적 필드 또는 속성에 대 한 참조를 만들 수 있지만이를 위해서는 접두사 매핑이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="8a292-123">Xaml 네임 스페이스는 거의 항상 XAML 문서의 루트 요소에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="8a292-124">정적 속성에 대 한 조회 작업은 기본 XAML 스키마 컨텍스트를 사용 하 여 실행 될 때 .NET XAML 서비스 및 XAML 판독기와 XAML 작성기에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="8a292-125">이 XAML 스키마 컨텍스트는 CLR 리플렉션을 사용 하 여 개체 그래프 생성에 필요한 정적 값을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="8a292-126">`typeName`사용자가 지정 하는는 실제로는 기본 xaml 스키마 컨텍스트를 사용할 때 또는 기존의 모든 clr 기반 xaml 구현 프레임 워크를 사용 하는 경우 동일한 이름 이지만 clr 형식 이름이 아니라 XAML 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="8a292-127">속성 값의 형식이 아닌 참조를 사용 하는 경우 주의 해야 `x:Static` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="8a292-128">XAML 처리 시퀀스에서 태그 확장의 제공 된 값은 추가 값 변환을 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="8a292-129">이는 참조가 텍스트 문자열을 만드는 경우에도 마찬가지 `x:Static` 이며 텍스트 문자열을 기반으로 하는 특성 값에 대 한 값 변환은 일반적으로 해당 특정 멤버나 반환 형식의 멤버 값에 대해 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="8a292-130">특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="8a292-131">`x:Static` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.StaticExtension.Member%2A> 확장명 클래스의 <xref:System.Windows.Markup.StaticExtension> 값으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="8a292-132">기술적으로 가능한 두 가지 XAML 사용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="8a292-133">그러나 이러한 사용은 불필요 하 게 자세한 정보를 표시 하기 때문에 더 일반적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="8a292-134">개체 요소 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="8a292-135">초기화 문자열의 명시적 멤버 속성이 포함 된 특성 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="8a292-136">.NET XAML 서비스 구현에서이 태그 확장에 대 한 처리는 클래스에 의해 정의 됩니다 <xref:System.Windows.Markup.StaticExtension> .</span><span class="sxs-lookup"><span data-stu-id="8a292-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="8a292-137">`x:Static`은 태그 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="8a292-138">XAML의 모든 태그 확장은 `{` `}` 특성 구문에서 및 문자를 사용 합니다 .이는 xaml 프로세서가 태그 확장에서 값을 제공 해야 함을 인식 하는 데 사용 되는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="8a292-139">태그 확장에 대한 자세한 내용은 [Markup Extensions for XAML Overview](markup-extensions-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a292-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="8a292-140">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="8a292-140">WPF Usage Notes</span></span>

<span data-ttu-id="8a292-141">WPF 프로그래밍에 사용 하는 기본 XAML 네임 스페이스에는 많은 유용한 정적 속성이 포함 되어 있지 않으며, 대부분의 유용한 정적 속성에는를 요구 하지 않고 사용을 용이 하 게 하는 형식 변환기와 같은 지원이 있습니다 `{x:Static}` .</span><span class="sxs-lookup"><span data-stu-id="8a292-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="8a292-142">정적 속성의 경우 다음 조건 중 하나에 해당 하는 경우에는 XAML 네임 스페이스에 대 한 접두사를 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="8a292-143">WPF에 존재 하지만 WPF에 대 한 기본 XAML 네임 스페이스의 일부가 아닌 형식을 참조 하는 경우 ( `http://schemas.microsoft.com/winfx/2006/xaml/presentation` )</span><span class="sxs-lookup"><span data-stu-id="8a292-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="8a292-144">이는를 사용 하는 매우 일반적인 시나리오입니다 `x:Static` .</span><span class="sxs-lookup"><span data-stu-id="8a292-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="8a292-145">예를 들어 `x:Static` <xref:System> 클래스의 정적 속성을 참조 하기 위해 CLR 네임 스페이스 및 mscorlib 어셈블리에 대 한 XAML 네임 스페이스 매핑과 함께 참조를 사용할 수 있습니다 <xref:System.Environment> .</span><span class="sxs-lookup"><span data-stu-id="8a292-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="8a292-146">사용자 지정 어셈블리에서 형식을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="8a292-147">WPF 어셈블리에 존재 하는 형식을 참조 하지만 해당 형식이 WPF 기본 XAML 네임 스페이스의 일부가 아닌 CLR 네임 스페이스 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a292-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="8a292-148">WPF의 기본 XAML 네임 스페이스에 대 한 CLR 네임 스페이스의 매핑은 다양 한 WPF 어셈블리의 정의에 의해 수행 됩니다 .이 개념에 대 한 자세한 내용은 [WPF xaml을 위한 Xaml 네임 스페이스 및 네임 스페이스 매핑](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a292-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)).</span></span> <span data-ttu-id="8a292-149">매핑되지 않은 CLR 네임 스페이스는 대개와 같이 일반적으로 XAML을 사용 하지 않는 대부분의 클래스 정의로 구성 되어 있는 경우에만 존재할 수 있습니다 <xref:System.Windows.Threading> .</span><span class="sxs-lookup"><span data-stu-id="8a292-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="8a292-150">WPF에 접두사 및 XAML 네임 스페이스를 사용 하는 방법에 대 한 자세한 내용은 [WPF xaml을 위한 Xaml 네임 스페이스 및 네임 스페이스 매핑](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a292-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](/dotnet/desktop/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a292-151">참조</span><span class="sxs-lookup"><span data-stu-id="8a292-151">See also</span></span>

- [<span data-ttu-id="8a292-152">x:Type 태그 확장</span><span class="sxs-lookup"><span data-stu-id="8a292-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="8a292-153">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="8a292-153">Types Migrated from WPF to System.Xaml</span></span>](/dotnet/desktop/wpf/advanced/types-migrated-from-wpf-to-system)
