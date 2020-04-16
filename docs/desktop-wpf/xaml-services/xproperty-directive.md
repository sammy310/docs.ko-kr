---
title: x:Property 지시문
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: 2804ec935d0626cba9ef050f70a3266cf23bcce0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432679"
---
# <a name="xproperty-directive"></a><span data-ttu-id="aa57c-102">x:Property 지시문</span><span class="sxs-lookup"><span data-stu-id="aa57c-102">x:Property Directive</span></span>

<span data-ttu-id="aa57c-103">태그로 XAML 속성을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-103">Declares a XAML property in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="aa57c-104">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="aa57c-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="aa57c-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="aa57c-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="aa57c-106">XAML 프로덕션에 대한 지원 클래스 또는 partial 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`propertyName`|<span data-ttu-id="aa57c-107">정의되는 속성의 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-107">Member name of the property being defined.</span></span>|
|`propertyType`|<span data-ttu-id="aa57c-108">이 속성의 형식을 지정하는 형식 이름(또는 프레임워크별 다른 문자열 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa57c-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa57c-109">Remarks</span></span>

<span data-ttu-id="aa57c-110">.NET XAML 서비스 구현에서 .</span><span class="sxs-lookup"><span data-stu-id="aa57c-110">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="aa57c-111">`x:Property`는 직접적인 형식 지원이 없지만 <xref:System.Windows.Markup.PropertyDefinition> 클래스에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="aa57c-112">XAML 노드 스트림에서 `x:Property` 요소는 XAML 언어 XAML 네임스페이스의 `Property`라는 멤버로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="aa57c-113">`Property` 멤버는 태그로 선언된 특성을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-113">The member `Property` hold attributes as declared by markup.</span></span>

<span data-ttu-id="aa57c-114">.NET `Name` XAML 서비스 수준에서 할당되지 않은 의미입니다. `Type`</span><span class="sxs-lookup"><span data-stu-id="aa57c-114">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="aa57c-115">나중에 특정 프레임워크에서 적용할 수 있는 규칙으로 해석되기 위해 초기 XAML 노드 스트림에 문자열 값으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="aa57c-116">의미는 XAML 이름 및 XAML 형식 의미와 일치되거나, 구현에 따라 지원 형식 시스템에서만 유효할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="aa57c-117">태그로 멤버 정의를 지정하기 위한 수단으로서 `x:Members`의 실제 사용을 지원하려면 멤버가 수정할 수 있는 클래스와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="aa57c-118">의도한 모델은 `x:Members`가 `x:Class`를 지정하는 형식의 멤버로 존재하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="aa57c-119">그러나 형식 및 멤버를 연결하거나 동적 멤버 정의를 생성하기 위한 메커니즘은 .NET XAML 서비스 수준에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="aa57c-120">이 작업은 XAML의 멤버 정의를 지원하는 애플리케이션 모델이 있는 개별 프레임워크에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="aa57c-121">일반적으로 해당 기능을 지원하려면 XAML을 태그로 컴파일하고 코드 숨김과 통합하거나 XAML 어셈블리에서만 생성하는 MSBUILD 빌드 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="aa57c-122">Windows Workflow Foundation에 대한 x:Property</span><span class="sxs-lookup"><span data-stu-id="aa57c-122">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="aa57c-123">Windows Workflow Foundation에서 `x:Property`는 XAML로만 작성된 사용자 지정 활동의 멤버 또는 코드 숨김을 사용하여 활동 디자이너에 대해 XAML로 정의된 동적 멤버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="aa57c-124">또한 XAML 프로덕션의 루트 요소에 `x:Class`를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="aa57c-125">이는 .NET XAML 서비스 수준에서 요구되는 것은 아니지만 일반적으로 사용자 지정 활동 및 Windows 워크플로 파운데이션 XAML을 지원하는 MSBUILD 빌드 작업에 의해 XAML 프로덕션이 로드될 때 요구 사항이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-125">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="aa57c-126">Windows 워크플로 파운데이션은 순수 XAML 형식 `x:Property` `Type` 이름을 특성에 대한 의도된 값으로 사용하지 않고 여기에 설명되지 않은 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aa57c-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="aa57c-127">자세한 내용은 [DynamicActivity 생성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aa57c-127">For more information, see [DynamicActivity Creation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
