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
ms.openlocfilehash: fdbc69634e86992e71cfccdc080829b6b45f963c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100932"
---
# <a name="xclassmodifier-directive"></a><span data-ttu-id="f22ea-102">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="f22ea-102">x:ClassModifier Directive</span></span>
<span data-ttu-id="f22ea-103">XAML 컴파일 동작을 수정 하는 경우 `x:Class` 도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-103">Modifies XAML compilation behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="f22ea-104">특히 부분을 만드는 대신 `class` 있는 `Public` 액세스 수준 (기본값), 제공 된 `x:Class` 만들어집니다는 `NotPublic` 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-104">Specifically, instead of creating a partial `class` that has a `Public` access level (the default), the provided `x:Class` is created with a `NotPublic` access level.</span></span> <span data-ttu-id="f22ea-105">이 동작에는 생성된 된 어셈블리의 클래스에 대 한 액세스 수준에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-105">This behavior affects the access level for the class in the generated assemblies.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f22ea-106">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="f22ea-106">XAML Attribute Usage</span></span>  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="f22ea-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="f22ea-107">XAML Values</span></span>  
  
|||  
|-|-|  
|*<span data-ttu-id="f22ea-108">NotPublic</span><span class="sxs-lookup"><span data-stu-id="f22ea-108">NotPublic</span></span>*|<span data-ttu-id="f22ea-109">정확한 문자열을 지정 하기 위해 전달 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 비교 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 하는 코드 숨김 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-109">The exact string to pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that you use.</span></span> <span data-ttu-id="f22ea-110">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f22ea-110">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="f22ea-111">종속성</span><span class="sxs-lookup"><span data-stu-id="f22ea-111">Dependencies</span></span>  
 <span data-ttu-id="f22ea-112">[X:class](x-class-directive.md) 동일한 요소에도 제공 해야 하며 해당 요소는 페이지의 루트 요소 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-112">[x:Class](x-class-directive.md) must also be provided on the same element, and that element must be the root element in a page.</span></span> <span data-ttu-id="f22ea-113">자세한 내용은 [ \[MS XAML\] 4.3.1.8 섹션](https://go.microsoft.com/fwlink/?LinkId=114525)합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-113">For more information, see [\[MS-XAML\] Section 4.3.1.8](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f22ea-114">설명</span><span class="sxs-lookup"><span data-stu-id="f22ea-114">Remarks</span></span>  
 <span data-ttu-id="f22ea-115">변수의 `x:ClassModifier` .NET Framework XAML 서비스의 사용 프로그래밍 언어에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-115">The value of `x:ClassModifier` in .NET Framework XAML Services usage varies by programming language.</span></span> <span data-ttu-id="f22ea-116">문자열을 사용 하 여 각 언어 구현 하는 방법에 따라 달라 집니다 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 및 반환에 대 한 의미를 정의 하는 형식 변환기 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, 해당 언어는 대/소문자 구분 여부 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-116">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
-   <span data-ttu-id="f22ea-117">C#, 문자열 지정에 전달할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 는 `internal`합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-117">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `internal`.</span></span>  
  
-   <span data-ttu-id="f22ea-118">Microsoft Visual Basic.net에서 문자열 지정에 전달할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 는 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-118">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is `Friend`.</span></span>  
  
-   <span data-ttu-id="f22ea-119">에 대 한 [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], 대상이 없습니다. 존재 XAML 컴파일을 지 원하는; 따라서 전달할 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-119">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets exist that support compiling XAML; therefore, the value to pass is unspecified.</span></span>  
  
 <span data-ttu-id="f22ea-120">지정할 수도 있습니다 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` C#에서는 `Public` Visual Basic의) 하지만 지정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 때문에 자주 수행 됩니다 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 이미 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-120">You can also specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> (`public` in C#, `Public` in Visual Basic); however, specifying <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is infrequently done because <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is already the default behavior.</span></span>  
  
 <span data-ttu-id="f22ea-121">다른 값을 해당 하는 사용자 코드를 사용 하 여 액세스 수준 제한 사항 등 `private` C#에서 관련이 없는 `x:ClassModifier` 중첩된 클래스 참조 XAML을에서 지원 되지 않으므로 따라서는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 한정자는 동일한 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-121">Other values with equivalent user code access-level restrictions, such as `private` in C#, are not relevant for `x:ClassModifier` because nested class references are not supported in XAML, and therefore, the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> modifier has the same effect.</span></span>  
  
## <a name="security-notes"></a><span data-ttu-id="f22ea-122">보안 정보</span><span class="sxs-lookup"><span data-stu-id="f22ea-122">Security Notes</span></span>  
 <span data-ttu-id="f22ea-123">에 선언 된 액세스 수준을 `x:ClassModifier` 특정 프레임 워크와 해당 기능에서 여전히 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-123">The access level as declared in `x:ClassModifier` is still subject to interpretation by particular frameworks and their capabilities.</span></span> <span data-ttu-id="f22ea-124">WPF에 로드 하 고 형식을 인스턴스화하는 기능이 포함 되어 있습니다. 여기서 `x:ClassModifier` 는 `internal`pack URI 참조를 통해 WPF 리소스에서 해당 클래스를 참조 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="f22ea-124">WPF includes capabilities to load and instantiate types where `x:ClassModifier` is `internal`, if that class is referenced from a WPF resource through a pack URI reference.</span></span> <span data-ttu-id="f22ea-125">이 경우를 잠재적으로 다른 프레임 워크에 의해 구현 된와 같은 다른 결과로 수행에 의존 하지 `x:ClassModifier` 가능한 모든 인스턴스화를 차단 하도록 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22ea-125">As a consequence of this case and potentially others like it implemented by other frameworks, do not rely exclusively on `x:ClassModifier` to block all possible instantiation attempts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22ea-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="f22ea-126">See also</span></span>

- [<span data-ttu-id="f22ea-127">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="f22ea-127">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="f22ea-128">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="f22ea-128">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="f22ea-129">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="f22ea-129">x:FieldModifier Directive</span></span>](x-fieldmodifier-directive.md)
- [<span data-ttu-id="f22ea-130">보안(WPF)</span><span class="sxs-lookup"><span data-stu-id="f22ea-130">Security (WPF)</span></span>](../wpf/security-wpf.md)
- [<span data-ttu-id="f22ea-131">WPF에서 System.Xaml로 마이그레이션된 형식</span><span class="sxs-lookup"><span data-stu-id="f22ea-131">Types Migrated from WPF to System.Xaml</span></span>](types-migrated-from-wpf-to-system-xaml.md)
