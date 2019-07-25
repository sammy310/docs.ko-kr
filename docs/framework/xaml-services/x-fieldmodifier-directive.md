---
title: x:FieldModifier 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484730"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="fcd35-102">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="fcd35-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="fcd35-103">명명 된 개체 참조에 대 한 필드가 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 기본 동작 대신 access로 정의 되도록 XAML 컴파일 동작을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="fcd35-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="fcd35-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="fcd35-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="fcd35-105">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fcd35-106">*공개*</span><span class="sxs-lookup"><span data-stu-id="fcd35-106">*Public*</span></span>|<span data-ttu-id="fcd35-107"><xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 지정<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 하기 위해 전달 하는 정확한 문자열은 사용 되는 코드 지향 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="fcd35-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fcd35-108">See Remarks.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="fcd35-109">종속성</span><span class="sxs-lookup"><span data-stu-id="fcd35-109">Dependencies</span></span>  
 <span data-ttu-id="fcd35-110">Xaml 프로덕션에서 아무 곳 `x:FieldModifier` 이나 사용 하는 경우 해당 xaml 프로덕션의 루트 요소는 [x:Class 지시문](x-class-directive.md)을 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](x-class-directive.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcd35-111">설명</span><span class="sxs-lookup"><span data-stu-id="fcd35-111">Remarks</span></span>  
 <span data-ttu-id="fcd35-112">`x:FieldModifier`는 클래스 또는 해당 멤버의 일반 액세스 수준을 선언 하는 것과 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="fcd35-113">Xaml 프로덕션의 일부인 특정 XAML 개체가 처리 되 고 응용 프로그램의 개체 그래프에서 잠재적으로 액세스할 수 있는 개체가 되는 경우 XAML 처리 동작과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="fcd35-114">기본적으로 이러한 개체에 대 한 필드 참조는 private으로 유지 되므로 컨트롤 소비자는 개체 그래프를 직접 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="fcd35-115">대신, 컨트롤 소비자는 레이아웃 루트, 자식 요소 컬렉션, 전용 공용 속성 등을 가져오는 등의 프로그래밍 모델에 사용 되는 표준 패턴을 사용 하 여 개체 그래프를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>  
  
 <span data-ttu-id="fcd35-116">`x:FieldModifier` 특성의 값은 프로그래밍 언어에 따라 다르며 용도는 특정 프레임 워크에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="fcd35-117">사용할 문자열은 각 언어 <xref:System.CodeDom.Compiler.CodeDomProvider> 에서 및 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>에 대 한 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 의미를 정의 하기 위해 반환 하는 형식 변환기와 해당 언어가 대/소문자를 구분 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>  
  
- <span data-ttu-id="fcd35-118">의 C#경우를 지정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 하기 위해 전달할 문자열은 `public`입니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>  
  
- <span data-ttu-id="fcd35-119">Microsoft Visual Basic .net의 경우를 지정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`하기 위해 전달할 문자열은입니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>  
  
- <span data-ttu-id="fcd35-120">/Cli C++의 경우 XAML에 대 한 대상이 현재 존재 하지 않습니다. 따라서 전달할 문자열이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-120">For C++/CLI, no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>  
  
 <span data-ttu-id="fcd35-121">( <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `Friend` <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `NotPublic` 의 경우 C#) Visual Basic를 지정할 수도 있지만, 동작이 이미 기본값 이기 때문에를 지정 하는 것은 비정상입니다.`internal`</span><span class="sxs-lookup"><span data-stu-id="fcd35-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>  
  
 <span data-ttu-id="fcd35-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>는 XAML을 컴파일한 어셈블리 외부의 코드에는 XAML 생성 요소에 대 한 액세스 권한이 필요 하기 때문에 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="fcd35-123">WPF 보안 아키텍처는 XAML 컴파일 동작과 함께 공용 액세스 `x:FieldModifier` 를 허용 하도록를 특별히 설정 하지 않는 한, 요소 인스턴스를 공용으로 저장 하는 필드를 선언 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>  
  
 <span data-ttu-id="fcd35-124">`x:FieldModifier`는 public 인 필드를 참조 하는 데 사용 되므로 [X:Name 지시문](x-name-directive.md) 이 있는 요소에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](x-name-directive.md) because that name is used to reference the field after it is public.</span></span>  
  
 <span data-ttu-id="fcd35-125">기본적으로 루트 요소에 대 한 partial 클래스는 public입니다. 그러나 [X:classmodifier 지시어](x-classmodifier-directive.md)를 사용 하 여 public을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span> <span data-ttu-id="fcd35-126">[X:classmodifier 지시문](x-classmodifier-directive.md) 은 루트 요소 클래스 인스턴스의 액세스 수준에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-126">The [x:ClassModifier Directive](x-classmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="fcd35-127">Root 요소에 및 `x:Name` `x:FieldModifier` 를 둘 다 넣을 수 있지만이 경우 root 요소의 public 필드 복사본만 적용 됩니다 .이는 true 루트 요소 클래스 액세스 수준이 [x:classmodifier 지시문](x-classmodifier-directive.md)에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcd35-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](x-classmodifier-directive.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd35-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="fcd35-128">See also</span></span>

- [<span data-ttu-id="fcd35-129">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="fcd35-129">XAML and Custom Classes for WPF</span></span>](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="fcd35-130">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="fcd35-130">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="fcd35-131">x:Name 지시문</span><span class="sxs-lookup"><span data-stu-id="fcd35-131">x:Name Directive</span></span>](x-name-directive.md)
- [<span data-ttu-id="fcd35-132">WPF 응용 프로그램 빌드(WPF)</span><span class="sxs-lookup"><span data-stu-id="fcd35-132">Building a WPF Application (WPF)</span></span>](../wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="fcd35-133">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="fcd35-133">x:ClassModifier Directive</span></span>](x-classmodifier-directive.md)
