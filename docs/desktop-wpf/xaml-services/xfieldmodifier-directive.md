---
title: x:FieldModifier 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 4e67a6dac49b8d6a7d316526f99a1519b08fd68b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554477"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="065da-102">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="065da-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="065da-103">명명 된 개체 참조에 대 한 필드가 기본 동작 대신 access로 정의 되도록 XAML 컴파일 동작을 수정 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="065da-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="065da-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="065da-104">XAML Attribute Usage</span></span>

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a><span data-ttu-id="065da-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="065da-105">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="065da-106">*공용*</span><span class="sxs-lookup"><span data-stu-id="065da-106">*Public*</span></span>|<span data-ttu-id="065da-107">지정 하기 위해 전달 하는 정확한 문자열은 사용 되는 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 코드 지향 프로그래밍 언어에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="065da-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="065da-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="065da-108">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="065da-109">종속성</span><span class="sxs-lookup"><span data-stu-id="065da-109">Dependencies</span></span>

 <span data-ttu-id="065da-110">XAML 프로덕션에서 아무 곳 이나 사용 하는 경우 `x:FieldModifier` 해당 xaml 프로덕션의 루트 요소는 [x:Class 지시문](xclass-directive.md)을 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="065da-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](xclass-directive.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="065da-111">설명</span><span class="sxs-lookup"><span data-stu-id="065da-111">Remarks</span></span>

<span data-ttu-id="065da-112">`x:FieldModifier` 는 클래스 또는 해당 멤버의 일반 액세스 수준을 선언 하는 것과 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="065da-113">Xaml 프로덕션의 일부인 특정 XAML 개체가 처리 되 고 응용 프로그램의 개체 그래프에서 잠재적으로 액세스할 수 있는 개체가 되는 경우 XAML 처리 동작과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="065da-114">기본적으로 이러한 개체에 대 한 필드 참조는 private으로 유지 되므로 컨트롤 소비자는 개체 그래프를 직접 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="065da-115">대신, 컨트롤 소비자는 레이아웃 루트, 자식 요소 컬렉션, 전용 공용 속성 등을 가져오는 등의 프로그래밍 모델에 사용 되는 표준 패턴을 사용 하 여 개체 그래프를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="065da-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>

<span data-ttu-id="065da-116">특성의 값은 `x:FieldModifier` 프로그래밍 언어에 따라 다르며 용도는 특정 프레임 워크에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="065da-117">사용할 문자열은 각 언어에서 및 <xref:System.CodeDom.Compiler.CodeDomProvider> 에 대 한 의미를 정의 하기 위해 반환 하는 형식 변환기와 해당 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 언어가 대/소문자를 구분 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="065da-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="065da-118">C #의 경우를 지정 하기 위해 전달할 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 은 `public` 입니다.</span><span class="sxs-lookup"><span data-stu-id="065da-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>

- <span data-ttu-id="065da-119">Microsoft Visual Basic .NET의 경우를 지정 하기 위해 전달할 문자열 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 은 `Public` 입니다.</span><span class="sxs-lookup"><span data-stu-id="065da-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>

- <span data-ttu-id="065da-120">C + +/CLI의 경우 현재 XAML의 대상이 없습니다. 따라서 전달할 문자열이 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-120">For C++/CLI, no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>

<span data-ttu-id="065da-121"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>( `internal` C #의 경우 Visual Basic)를 지정할 수도 `Friend` 있지만 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> `NotPublic` , 동작은 이미 기본값 이기 때문에를 지정 하는 것은 비정상입니다.</span><span class="sxs-lookup"><span data-stu-id="065da-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>

<span data-ttu-id="065da-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 는 XAML을 컴파일한 어셈블리 외부의 코드에는 XAML 생성 요소에 대 한 액세스 권한이 필요 하기 때문에 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="065da-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="065da-123">WPF 보안 아키텍처는 XAML 컴파일 동작과 함께 `x:FieldModifier` 공용 액세스를 허용 하도록를 특별히 설정 하지 않는 한, 요소 인스턴스를 공용으로 저장 하는 필드를 선언 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>

<span data-ttu-id="065da-124">`x:FieldModifier` 는 public 인 필드를 참조 하는 데 사용 되므로 [X:Name 지시문](xname-directive.md) 이 있는 요소에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="065da-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](xname-directive.md) because that name is used to reference the field after it is public.</span></span>

<span data-ttu-id="065da-125">기본적으로 루트 요소에 대 한 partial 클래스는 public입니다. 그러나 [X:classmodifier 지시어](xclassmodifier-directive.md)를 사용 하 여 public을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="065da-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span> <span data-ttu-id="065da-126">[X:classmodifier 지시문](xclassmodifier-directive.md) 은 루트 요소 클래스 인스턴스의 액세스 수준에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="065da-126">The [x:ClassModifier Directive](xclassmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="065da-127">Root 요소에 및를 둘 다 넣을 수 있지만이 경우 root 요소의 `x:Name` `x:FieldModifier` public 필드 복사본만 적용 됩니다 .이는 true 루트 요소 클래스 액세스 수준이 [X:classmodifier 지시문](xclassmodifier-directive.md)에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="065da-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="065da-128">참조</span><span class="sxs-lookup"><span data-stu-id="065da-128">See also</span></span>

- [<span data-ttu-id="065da-129">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="065da-129">XAML and Custom Classes for WPF</span></span>](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
- [<span data-ttu-id="065da-130">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="065da-130">Code-Behind and XAML in WPF</span></span>](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [<span data-ttu-id="065da-131">x:Name 지시문</span><span class="sxs-lookup"><span data-stu-id="065da-131">x:Name Directive</span></span>](xname-directive.md)
- [<span data-ttu-id="065da-132">WPF 애플리케이션 빌드(WPF)</span><span class="sxs-lookup"><span data-stu-id="065da-132">Building a WPF Application (WPF)</span></span>](/dotnet/desktop/wpf/app-development/building-a-wpf-application-wpf)
- [<span data-ttu-id="065da-133">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="065da-133">x:ClassModifier Directive</span></span>](xclassmodifier-directive.md)
