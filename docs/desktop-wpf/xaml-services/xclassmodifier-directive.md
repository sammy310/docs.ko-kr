---
title: x:ClassModifier 지시문
ms.date: 03/30/2017
f1_keywords:
- xClassModifier
- x:ClassModifier
- ClassModifier
helpviewer_keywords:
- XAML [XAML Services], x:ClassModifier attribute
- x:ClassModifier attribute [XAML Services]
- ClassModifier attribute in XAML [XAML Services]
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
ms.openlocfilehash: 436204774c2d59b43a77865c666aed702f7681db
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "81433273"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="9cc9d-102">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="9cc9d-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="9cc9d-103">XAML 컴파일 동작도 제공된 `x:Class` 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="9cc9d-104">`class` 특히 `Public` 액세스 수준(기본값)이 있는 부분을 만드는 대신 `x:Class` 제공된 `NotPublic` 액세스 수준이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="9cc9d-105">이 동작은 생성된 어셈블리의 클래스에 대한 액세스 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-105">This behavior affects the access level for the class in the generated assemblies.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="9cc9d-106">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="9cc9d-106">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="9cc9d-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="9cc9d-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="9cc9d-108">*비공개 아님*</span><span class="sxs-lookup"><span data-stu-id="9cc9d-108">*NotPublic*</span></span>|<span data-ttu-id="9cc9d-109">지정할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 정확한 문자열과 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 지정하는 문자열은 사용하는 코드 숨김 프로그래밍 언어에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="9cc9d-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-110">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="9cc9d-111">종속성</span><span class="sxs-lookup"><span data-stu-id="9cc9d-111">Dependencies</span></span>

<span data-ttu-id="9cc9d-112">[x:Class는](xclass-directive.md) 동일한 요소에도 제공되어야 하며 해당 요소는 페이지의 루트 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-112">[x:Class](xclass-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="9cc9d-113">자세한 내용은 [ \[MS-XAML\] 섹션 4.3.1.8을](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="remarks"></a><span data-ttu-id="9cc9d-114">설명</span><span class="sxs-lookup"><span data-stu-id="9cc9d-114">Remarks</span></span>

<span data-ttu-id="9cc9d-115">.NET `x:ClassModifier` XAML 서비스 사용의 가치는 프로그래밍 언어에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-115">The value of `x:ClassModifier` in .NET XAML Services usage varies by programming language.</span></span> <span data-ttu-id="9cc9d-116">사용할 문자열은 각 언어가 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 언어를 구현하는 방법과 해당 언어가 반환하는 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>형식 변환기의 의미를 정의하고 해당 언어가 대/소문자를 구분하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="9cc9d-117">C#의 경우 지정할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 문자열은 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>

- <span data-ttu-id="9cc9d-118">Microsoft Visual Basic .NET의 경우 지정할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 문자열은 `Friend`.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>

- <span data-ttu-id="9cc9d-119">C++/CLI의 경우 XAML 컴파일을 지원하는 대상이 없습니다. 따라서 전달할 값은 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>

<span data-ttu-id="9cc9d-120">(C#에서 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `public` `Public` 시각적 기본)을 지정할 수도 있습니다. 그러나 이미 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 기본 동작이기 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 때문에 지정하는 작업은 자주 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>

<span data-ttu-id="9cc9d-121">C#과 같이 `private` 동일한 사용자 코드 액세스 수준 제한이 있는 다른 `x:ClassModifier` 값은 중첩된 클래스 참조가 XAML에서 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 지원되지 않으므로 수정자는 동일한 효과를 가지므로 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>

## <a name="security-notes"></a><span data-ttu-id="9cc9d-122">보안 정보</span><span class="sxs-lookup"><span data-stu-id="9cc9d-122">Security Notes</span></span>

<span data-ttu-id="9cc9d-123">에 `x:ClassModifier` 선언된 액세스 수준은 여전히 특정 프레임워크 및 해당 기능에 의해 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="9cc9d-124">WPF에는 해당 클래스가 WPF 리소스에서 `internal`팩 URI 참조를 통해 참조되는 경우 형식을 `x:ClassModifier` 로드하고 인스턴스화하는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="9cc9d-125">이 사례와 다른 프레임워크에서 구현한 것과 같은 잠재적으로 다른 작업의 결과로 `x:ClassModifier` 가능한 모든 인스턴스화 시도를 차단하는 데만 의존하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9cc9d-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>

## <a name="see-also"></a><span data-ttu-id="9cc9d-126">참조</span><span class="sxs-lookup"><span data-stu-id="9cc9d-126">See also</span></span>

- [<span data-ttu-id="9cc9d-127">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="9cc9d-127">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="9cc9d-128">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="9cc9d-128">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="9cc9d-129">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="9cc9d-129">x:FieldModifier Directive</span></span>](xfieldmodifier-directive.md)
- [<span data-ttu-id="9cc9d-130">보안(WPF)</span><span class="sxs-lookup"><span data-stu-id="9cc9d-130">Security (WPF)</span></span>](../../framework/wpf/security-wpf.md)
- [<span data-ttu-id="9cc9d-131">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="9cc9d-131">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
