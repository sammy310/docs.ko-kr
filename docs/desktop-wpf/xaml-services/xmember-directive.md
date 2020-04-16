---
title: x:Member 지시문
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: e82bb6397404ee466a12ab438585ae1898c34d1a
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432733"
---
# <a name="xmember-directive"></a><span data-ttu-id="0c3fd-102">x:Member 지시문</span><span class="sxs-lookup"><span data-stu-id="0c3fd-102">x:Member Directive</span></span>
<span data-ttu-id="0c3fd-103">태그로 XAML 멤버를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-103">Declares a XAML member in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="0c3fd-104">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="0c3fd-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="0c3fd-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="0c3fd-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="0c3fd-106">XAML 프로덕션에 대한 지원 클래스 또는 partial 클래스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`memberName`|<span data-ttu-id="0c3fd-107">정의되는 속성의 멤버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-107">Member name of the property being defined.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0c3fd-108">설명</span><span class="sxs-lookup"><span data-stu-id="0c3fd-108">Remarks</span></span>

<span data-ttu-id="0c3fd-109">.NET XAML 서비스 구현에서 .</span><span class="sxs-lookup"><span data-stu-id="0c3fd-109">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="0c3fd-110">`x:Member`는 직접적인 형식 지원이 없지만 <xref:System.Windows.Markup.MemberDefinition> 클래스에 의해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="0c3fd-111">XAML 노드 스트림에서 `x:Member` 요소는 XAML 언어 XAML 네임스페이스의 `Member`라는 멤버로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="0c3fd-112">`Member` 멤버는 태그로 선언된 특성을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-112">The member `Member` holds attributes as declared by markup.</span></span>

<span data-ttu-id="0c3fd-113">.NET `Name` XAML 서비스 수준에서 할당되지 않은 의미입니다. `Type`</span><span class="sxs-lookup"><span data-stu-id="0c3fd-113">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="0c3fd-114">나중에 특정 프레임워크에서 적용할 수 있는 규칙으로 해석되기 위해 초기 XAML 노드 스트림에 문자열 값으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="0c3fd-115">의미는 XAML 이름 및 XAML 형식 의미와 일치되거나, 구현에 따라 지원 형식 시스템에서만 유효할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="0c3fd-116">태그로 멤버 정의를 지정하기 위한 수단으로서 `x:Members`의 실제 사용을 지원하려면 멤버가 수정할 수 있는 클래스와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="0c3fd-117">의도한 모델은 `x:Members`가 `x:Class`를 지정하는 형식의 멤버로 존재하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="0c3fd-118">그러나 형식 및 멤버를 연결하거나 동적 멤버 정의를 생성하기 위한 메커니즘은 .NET XAML 서비스 수준에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="0c3fd-119">이 작업은 XAML의 멤버 정의를 지원하는 애플리케이션 모델이 있는 개별 프레임워크에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="0c3fd-120">일반적으로 해당 기능을 지원하려면 XAML을 태그로 컴파일하고 코드 숨김과 통합하거나 XAML 어셈블리에서만 생성하는 MSBUILD 빌드 작업이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="0c3fd-121">Windows Workflow Foundation에 대한 x:Property</span><span class="sxs-lookup"><span data-stu-id="0c3fd-121">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="0c3fd-122">Windows Workflow Foundation에서 `x:Property`는 XAML로만 작성된 사용자 지정 활동의 멤버 또는 코드 숨김을 사용하여 활동 디자이너에 대해 XAML로 정의된 동적 멤버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="0c3fd-123">또한 XAML 프로덕션의 루트 요소에 `x:Class`를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="0c3fd-124">이는 .NET XAML 서비스 수준에서 요구되는 것은 아니지만 일반적으로 사용자 지정 활동 및 Windows 워크플로 파운데이션 XAML을 지원하는 MSBUILD 빌드 작업에 의해 XAML 프로덕션이 로드될 때 요구 사항이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-124">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="0c3fd-125">Windows 워크플로 파운데이션은 순수 XAML 형식 `x:Property` `Type` 이름을 특성에 대한 의도된 값으로 사용하지 않고 여기에 설명되지 않은 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="0c3fd-126">자세한 내용은 [DynamicActivity 생성](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100))을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0c3fd-126">For more information, see [DynamicActivity Creation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
