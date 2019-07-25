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
ms.openlocfilehash: c3c08f61b49a6367663cf02099dda86d1a692284
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484756"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="79d4a-102">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="79d4a-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="79d4a-103">가 제공 되는 경우 `x:Class` XAML 컴파일 동작을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="79d4a-104">특히 `class` `Public` 액세스 수준이 있는 부분 (기본값)을 만드는 대신 `NotPublic` 제공 `x:Class` 된이 액세스 수준으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="79d4a-105">이 동작은 생성 된 어셈블리의 클래스에 대 한 액세스 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="79d4a-106">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="79d4a-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="79d4a-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="79d4a-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79d4a-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="79d4a-108">*NotPublic*</span></span>|<span data-ttu-id="79d4a-109">를 사용 하 여 지정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 하기 위해 전달할 정확한 문자열은 사용 하는 코드 지향 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="79d4a-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79d4a-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="79d4a-111">종속성</span><span class="sxs-lookup"><span data-stu-id="79d4a-111">Dependencies</span></span>  
 <span data-ttu-id="79d4a-112">또한 같은 요소에 [x:Class](x-class-directive.md) 를 제공 해야 하며,이 요소는 페이지의 루트 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="79d4a-113">자세한 내용은 [ \[4.3.1.8\] 섹션](https://go.microsoft.com/fwlink/?LinkId=114525)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="79d4a-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79d4a-114">설명</span><span class="sxs-lookup"><span data-stu-id="79d4a-114">Remarks</span></span>  
 <span data-ttu-id="79d4a-115">.NET Framework XAML 서비스 `x:ClassModifier` 사용의 값은 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="79d4a-116">사용할 문자열은 각 언어 <xref:System.CodeDom.Compiler.CodeDomProvider> 에서 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>에 대 한 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 의미를 정의 하기 위해 반환 하는 형식 변환기와 해당 언어가 대/소문자를 구분 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="79d4a-117">의 C#경우를 지정 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 하기 위해 전달할 문자열은 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="79d4a-118">Microsoft Visual Basic .net의 경우를 지정 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend`하기 위해 전달할 문자열은입니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="79d4a-119">/Cli C++의 경우 XAML 컴파일을 지 원하는 대상이 없습니다. 따라서 전달할 값이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="79d4a-120">( <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public` <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 의 경우) Visual Basic를 지정할 수도 있습니다. 그러나가 이미 기본 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 동작 이기 때문에를 지정 하는 것은 드물게 수행 됩니다. C#`public`</span><span class="sxs-lookup"><span data-stu-id="79d4a-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="79d4a-121">`private` C#에서와 같이 동등한 사용자 코드 액세스 수준 제한이 있는 다른 값은 XAML에서 중첩 된 클래스 참조가 `x:ClassModifier` 지원 되지 않기 때문에와 관련이 없으므로 한정자는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 동일한 효과를 가집니다. .</span><span class="sxs-lookup"><span data-stu-id="79d4a-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="79d4a-122">보안 정보</span><span class="sxs-lookup"><span data-stu-id="79d4a-122">Security Notes</span></span>  
 <span data-ttu-id="79d4a-123">에 `x:ClassModifier` 선언 된 액세스 수준에는 여전히 특정 프레임 워크 및 해당 기능에 대 한 해석이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="79d4a-124">Wpf에는를 로드 하 고 인스턴스화할 수 `x:ClassModifier` 있는 `internal`기능이 포함 되어 있습니다. 여기서는 해당 클래스가 pack URI 참조를 통해 WPF 리소스에서 참조 되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="79d4a-125">이러한 경우와 다른 프레임 워크에서 구현 하는 것과 같은 다른 사용자에 게는에 `x:ClassModifier` 만 의존 하 여 가능한 모든 인스턴스화 시도를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="79d4a-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79d4a-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="79d4a-126">See also</span></span>

- [<span data-ttu-id="79d4a-127">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="79d4a-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="79d4a-128">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="79d4a-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="79d4a-129">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="79d4a-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="79d4a-130">보안 (WPF)</span><span class="sxs-lookup"><span data-stu-id="79d4a-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="79d4a-131">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="79d4a-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
