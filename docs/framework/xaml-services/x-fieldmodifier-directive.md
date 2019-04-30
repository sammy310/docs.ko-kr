---
title: x:FieldModifier 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: c20564bcf8a25b1b59887fbefe6419671e0d6c03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971873"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="61139-102">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="61139-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="61139-103">명명 된 개체 참조에 대 한 필드 정의 된 XAML 컴파일 동작을 수정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 대신 액세스는 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="61139-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="61139-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="61139-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="61139-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="61139-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="61139-106">*공용*</span><span class="sxs-lookup"><span data-stu-id="61139-106">*Public*</span></span>|<span data-ttu-id="61139-107">정확한 문자열 지정 전달할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 비교 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 사용 되는 코드 숨김 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="61139-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="61139-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61139-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="61139-109">종속성</span><span class="sxs-lookup"><span data-stu-id="61139-109">Dependencies</span></span>  
 <span data-ttu-id="61139-110">XAML 프로덕션에 사용 하는 경우 `x:FieldModifier` 어디서 나 해당 XAML 프로덕션의 루트 요소를 선언 해야 합니다는 [X:class 지시문](x-class-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61139-111">설명</span><span class="sxs-lookup"><span data-stu-id="61139-111">Remarks</span></span>  
 <span data-ttu-id="61139-112">`x:FieldModifier` 관련이 없는 클래스 또는 해당 멤버의 일반적인 액세스 수준을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="61139-113">이 경우 XAML 처리 동작에만 관련 XAML 프로덕션의 포함 된 특정 XAML 개체 처리 되 고 응용 프로그램의 개체 그래프에서 잠재적으로 액세스할 수 있는 개체가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61139-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="61139-114">기본적으로 개체 그래프를 직접 수정 컨트롤 소비자를 방지 하는 이러한 개체에 대 한 필드 참조를 비공개로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61139-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="61139-115">따라서 컨트롤 소비자는 레이아웃 루트, 자식 요소 컬렉션을 전용된 공용 속성을 가져와서와 같은 프로그래밍 모델에서 사용할 수 있는 표준 패턴을 사용 하 여 개체 그래프를 수정 해야 하는 등에입니다.</span><span class="sxs-lookup"><span data-stu-id="61139-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="61139-116">에 대 한 값을 `x:FieldModifier` 특성 프로그래밍 언어에 따라 다르며 용도 특정 프레임 워크에서 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61139-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="61139-117">문자열을 사용 하 여 각 언어 구현 하는 방법에 따라 달라 집니다 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 및 반환에 대 한 의미를 정의 하는 형식 변환기 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, 해당 언어는 대/소문자 구분 여부 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="61139-118">C#, 문자열 지정에 전달할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 는 `public`합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
- <span data-ttu-id="61139-119">Microsoft Visual Basic.net에서 문자열 지정에 전달할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 는 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
- <span data-ttu-id="61139-120">에 대 한 [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], XAML에 대 한 대상이 없습니다. 현재 존재 하며 따라서 전달할 문자열 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61139-120">For [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)], no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="61139-121">지정할 수도 있습니다 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` 에서 C#를 `Friend` Visual Basic의) 지정 하지만 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 일반적이 지 않습니다 때문에 `NotPublic` 동작은 이미 기본으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="61139-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 어셈블리 외부의 코드는 XAML 컴파일된 XAML에서 만든 요소에 액세스 해야 함을 자주 하지 않기 때문에 기본 동작이입니다.</span><span class="sxs-lookup"><span data-stu-id="61139-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="61139-123">XAML 컴파일 동작와 함께 WPF 보안 아키텍처를 설정 하지 않으면 공용으로 요소 인스턴스를 저장 하는 필드를 선언 하지는 `x:FieldModifier` 공용 액세스를 허용 하려면.</span><span class="sxs-lookup"><span data-stu-id="61139-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="61139-124">`x:FieldModifier` 관련이 사용 하 여 요소를 [X:name 지시문](x-name-directive.md) 공개 되 면 필드를 참조 하도록 해당 이름이 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61139-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="61139-125">기본적으로 루트 요소에 대 한 partial 클래스는 공용 필드 그러나 있습니다 수 있도록 public이 아닌를 사용 하 여 합니다 [X:classmodifier 지시문](x-classmodifier-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span> <span data-ttu-id="61139-126">합니다 [X:classmodifier 지시문](x-classmodifier-directive.md) 루트 요소 클래스의 인스턴스 액세스 수준에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61139-126">The [x:ClassModifier Directive](x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="61139-127">모두 넣을 수 있습니다 `x:Name` 하 고 `x:FieldModifier` 루트에서 요소에 있지만이 public 필드의 복사본을 만듭니다는 true 루트 요소 클래스 액세스 수준으로 여전히 루트 요소에 의해 제어 [X:classmodifier 지시문](x-classmodifier-directive.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61139-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61139-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="61139-128">See also</span></span>

- [<span data-ttu-id="61139-129">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="61139-129">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="61139-130">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="61139-130">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="61139-131">x:Name 지시문</span><span class="sxs-lookup"><span data-stu-id="61139-131">x:Name Directive</span></span>](x-name-directive.md)
- [<span data-ttu-id="61139-132">WPF 응용 프로그램 빌드(WPF)</span><span class="sxs-lookup"><span data-stu-id="61139-132">Building a WPF Application (WPF)</span></span>](../wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="61139-133">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="61139-133">x:ClassModifier Directive</span></span>](x-classmodifier-directive.md)
