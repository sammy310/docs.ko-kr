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
ms.openlocfilehash: a24277a4d5fbc4870157b6c8ba00ba71ba61e656
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837235"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="abb34-102">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="abb34-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="abb34-103">`x:Class` 제공 되는 경우 XAML 컴파일 동작을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="abb34-104">특히 `Public` 액세스 수준이 있는 부분 `class` (기본값)를 만드는 대신 제공 된 `x:Class` `NotPublic` 액세스 수준을 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="abb34-105">이 동작은 생성 된 어셈블리의 클래스에 대 한 액세스 수준에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="abb34-106">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="abb34-106">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="abb34-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="abb34-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="abb34-108">*NotPublic*</span><span class="sxs-lookup"><span data-stu-id="abb34-108">*NotPublic*</span></span>|<span data-ttu-id="abb34-109"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 지정 하기 위해 전달할 정확한 문자열은 사용 하는 코드 지향 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="abb34-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="abb34-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="abb34-111">종속성</span><span class="sxs-lookup"><span data-stu-id="abb34-111">Dependencies</span></span>  
 <span data-ttu-id="abb34-112">또한 같은 요소에 [x:Class](x-class-directive.md) 를 제공 해야 하며,이 요소는 페이지의 루트 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="abb34-113">자세한 내용은 [\[MS-XAML\] 섹션 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abb34-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abb34-114">주의</span><span class="sxs-lookup"><span data-stu-id="abb34-114">Remarks</span></span>  
 <span data-ttu-id="abb34-115">.NET Framework XAML 서비스 사용의 `x:ClassModifier` 값은 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="abb34-116">사용할 문자열은 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>에 대 한 의미 및 해당 언어가 대/소문자를 구분 하는지 여부를 정의 하기 위해 각 언어가 <xref:System.CodeDom.Compiler.CodeDomProvider>를 구현 하는 방법과 반환 하는 형식 변환기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="abb34-117">C#에서 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>을 지정 하기 위해 전달할 문자열은 `internal`입니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
- <span data-ttu-id="abb34-118">Microsoft Visual Basic .NET의 경우 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>을 지정 하기 위해 전달할 문자열이 `Friend`됩니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
- <span data-ttu-id="abb34-119">/Cli C++의 경우 XAML 컴파일을 지 원하는 대상이 없습니다. 따라서 전달할 값이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-119">For C++/CLI, no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="abb34-120"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` C#, `Public` Visual Basic)를 지정할 수도 있습니다. 그러나 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>가 이미 기본 동작 이기 때문에 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>를 지정 하는 것은 거의 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="abb34-121">에서 C#`private`와 같이 동등한 사용자 코드 액세스 수준 제한이 있는 다른 값은 XAML에서 중첩 클래스 참조가 지원 되지 않기 때문에 `x:ClassModifier`와 관련이 없으므로 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 한정자는 동일한 효과를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="abb34-122">보안 정보</span><span class="sxs-lookup"><span data-stu-id="abb34-122">Security Notes</span></span>  
 <span data-ttu-id="abb34-123">`x:ClassModifier`에 선언 된 액세스 수준은 여전히 특정 프레임 워크 및 해당 기능에 의해 해석 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="abb34-124">WPF에는 `x:ClassModifier` `internal`되는 형식을 로드 하 고 인스턴스화하는 기능이 포함 되어 있습니다. 해당 클래스가 pack URI 참조를 통해 WPF 리소스에서 참조 되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="abb34-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="abb34-125">이 경우 다른 프레임 워크에서 구현 하는 것과 같은 다른 사용자에 게는 가능한 모든 인스턴스화 시도를 차단 하는 `x:ClassModifier`만 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="abb34-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb34-126">참조</span><span class="sxs-lookup"><span data-stu-id="abb34-126">See also</span></span>

- [<span data-ttu-id="abb34-127">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="abb34-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="abb34-128">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="abb34-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="abb34-129">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="abb34-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="abb34-130">보안 (WPF)</span><span class="sxs-lookup"><span data-stu-id="abb34-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="abb34-131">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="abb34-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
