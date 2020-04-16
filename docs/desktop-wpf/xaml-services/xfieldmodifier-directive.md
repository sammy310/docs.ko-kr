---
title: x:FieldModifier 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 3e104b4c464d545e048f29901701c1c3dbb68229
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432781"
---
# <a name="xfieldmodifier-directive"></a><span data-ttu-id="1e2e3-102">x:FieldModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="1e2e3-102">x:FieldModifier Directive</span></span>
<span data-ttu-id="1e2e3-103">명명된 개체 참조에 대한 필드가 기본 동작 대신 액세스로 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 정의되도록 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> XAML 컴파일 동작을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-103">Modifies XAML compilation behavior so that fields for named object references are defined with <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access instead of the <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> default behavior.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="1e2e3-104">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="1e2e3-104">XAML Attribute Usage</span></span>

```xaml
<object x:FieldModifier="Public".../>
```

## <a name="xaml-values"></a><span data-ttu-id="1e2e3-105">XAML 값</span><span class="sxs-lookup"><span data-stu-id="1e2e3-105">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="1e2e3-106">*공용*</span><span class="sxs-lookup"><span data-stu-id="1e2e3-106">*Public*</span></span>|<span data-ttu-id="1e2e3-107">지정하기 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 위해 전달하는 정확한 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 문자열과 사용되는 코드 숨김 프로그래밍 언어에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-107">The exact string you pass to specify <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> versus <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> varies, depending on the code-behind programming language that is used.</span></span> <span data-ttu-id="1e2e3-108">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-108">See Remarks.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="1e2e3-109">종속성</span><span class="sxs-lookup"><span data-stu-id="1e2e3-109">Dependencies</span></span>

 <span data-ttu-id="1e2e3-110">XAML 프로덕션에서 `x:FieldModifier` 어디서나 사용하는 경우 해당 XAML 프로덕션의 루트 요소는 [x:Class 지시문을](xclass-directive.md)선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-110">If a XAML production uses `x:FieldModifier` anywhere, the root element of that XAML production must declare an [x:Class Directive](xclass-directive.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="1e2e3-111">설명</span><span class="sxs-lookup"><span data-stu-id="1e2e3-111">Remarks</span></span>

<span data-ttu-id="1e2e3-112">`x:FieldModifier`은 클래스 또는 해당 구성원의 일반 액세스 수준을 선언하는 데 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-112">`x:FieldModifier` is not relevant for declaring the general access level of a class or its members.</span></span> <span data-ttu-id="1e2e3-113">XAML 프로덕션의 일부인 특정 XAML 개체가 처리되고 응용 프로그램의 개체 그래프에서 잠재적으로 액세스할 수 있는 개체가 되는 경우에만 XAML 처리 동작과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-113">It is relevant only for XAML-processing behavior when a particular XAML object that is part of a XAML production is processed, and becomes an object that is potentially accessible in the object graph of an application.</span></span> <span data-ttu-id="1e2e3-114">기본적으로 이러한 개체에 대한 필드 참조는 비공개로 유지되어 컨트롤 소비자가 개체 그래프를 직접 수정하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-114">By default, the field reference for such an object is kept private, which prevents control consumers from modifying the object graph directly.</span></span> <span data-ttu-id="1e2e3-115">대신 컨트롤 소비자는 레이아웃 루트, 자식 요소 컬렉션, 전용 공용 속성 등을 가져오는 등 프로그래밍 모델에 의해 활성화된 표준 패턴을 사용하여 개체 그래프를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-115">Instead, control consumers are expected to modify the object graph by using standard patterns that are enabled by programming models, such as by obtaining the layout root, the child element collections, the dedicated public properties, and so on.</span></span>

<span data-ttu-id="1e2e3-116">특성의 `x:FieldModifier` 값은 프로그래밍 언어에 따라 다르며 그 목적은 특정 프레임워크에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-116">The value for the `x:FieldModifier` attribute varies by programming language, and its purpose can vary in specific frameworks.</span></span> <span data-ttu-id="1e2e3-117">사용할 문자열은 각 언어가 해당 <xref:System.CodeDom.Compiler.CodeDomProvider> 언어를 구현하는 방법과 해당 언어가 반환하는 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>형식 변환기의 의미를 정의하고 해당 언어가 대/소문자를 구분하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-117">The string to use depends on how each language implements its <xref:System.CodeDom.Compiler.CodeDomProvider> and the type converters it returns to define the meanings for <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> and <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>, and whether that language is case sensitive.</span></span>

- <span data-ttu-id="1e2e3-118">C#의 경우 지정할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 문자열은 `public`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-118">For C#, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `public`.</span></span>

- <span data-ttu-id="1e2e3-119">Microsoft Visual Basic .NET의 경우 지정할 <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> 문자열은 `Public`.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-119">For Microsoft Visual Basic .NET, the string to pass to designate <xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> is `Public`.</span></span>

- <span data-ttu-id="1e2e3-120">C++/CLI의 경우 XAML에 대한 대상이 현재 존재하지 않습니다. 따라서 전달할 문자열이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-120">For C++/CLI, no targets for XAML currently exist; therefore, the string to pass is undefined.</span></span>

<span data-ttu-id="1e2e3-121"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 또한 (C#에서,`internal` `Friend` 시각적 기본에서) 지정할 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> 수 `NotPublic` 있지만 비헤이비어가 이미 기본값이므로 지정하는 것은 비정상입니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-121">You can also specify <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> (`internal` in C#, `Friend` in Visual Basic) but specifying <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is unusual because `NotPublic` as the behavior is already the default.</span></span>

<span data-ttu-id="1e2e3-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>XAML을 컴파일한 어셈블리 외부의 코드가 XAML에서 만든 요소에 액세스해야 하는 경우는 드물기 때문에 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-122"><xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> is the default behavior because it is infrequent that code outside the assembly that compiled the XAML needs access to a XAML-created element.</span></span> <span data-ttu-id="1e2e3-123">WPF 보안 아키텍처와 XAML 컴파일 동작은 공용 액세스를 `x:FieldModifier` 허용하도록 특별히 설정하지 않는 한 요소 인스턴스를 공용으로 저장하는 필드를 선언하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-123">WPF security architecture together with XAML compilation behavior will not declare fields that store element instances as public, unless you specifically set the `x:FieldModifier` to allow public access.</span></span>

<span data-ttu-id="1e2e3-124">`x:FieldModifier`해당 이름은 public 이후에 필드를 참조하는 데 사용되므로 [x:Name 지시문이](xname-directive.md) 있는 요소에만 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-124">`x:FieldModifier` is only relevant for elements with an [x:Name Directive](xname-directive.md) because that name is used to reference the field after it is public.</span></span>

<span data-ttu-id="1e2e3-125">기본적으로 루트 요소의 부분 클래스는 공용입니다. 그러나 [x:ClassModifier 지시문을](xclassmodifier-directive.md)사용하여 비공개로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-125">By default, the partial class for the root element is public; however, you can make it nonpublic by using the [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span> <span data-ttu-id="1e2e3-126">[x:ClassModifier 지시문은](xclassmodifier-directive.md) 루트 요소 클래스의 인스턴스의 액세스 수준에도 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-126">The [x:ClassModifier Directive](xclassmodifier-directive.md) also affects the access level of the instance of the root element class.</span></span> <span data-ttu-id="1e2e3-127">루트 요소와 `x:Name` `x:FieldModifier` 루트 요소에 모두 넣을 수 있지만, 이것은 진정한 루트 요소 클래스 액세스 수준이 여전히 [x:ClassModifier 지시문에](xclassmodifier-directive.md)의해 제어되는 루트 요소의 공용 필드 복사본만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e2e3-127">You can put both `x:Name` and `x:FieldModifier` on the root element, but this only makes a public field copy of the root element, with the true root element class access level still controlled by [x:ClassModifier Directive](xclassmodifier-directive.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e2e3-128">참조</span><span class="sxs-lookup"><span data-stu-id="1e2e3-128">See also</span></span>

- [<span data-ttu-id="1e2e3-129">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="1e2e3-129">XAML and Custom Classes for WPF</span></span>](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [<span data-ttu-id="1e2e3-130">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="1e2e3-130">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="1e2e3-131">x:Name 지시문</span><span class="sxs-lookup"><span data-stu-id="1e2e3-131">x:Name Directive</span></span>](xname-directive.md)
- [<span data-ttu-id="1e2e3-132">WPF 애플리케이션 빌드(WPF)</span><span class="sxs-lookup"><span data-stu-id="1e2e3-132">Building a WPF Application (WPF)</span></span>](../../framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="1e2e3-133">x:ClassModifier 지시문</span><span class="sxs-lookup"><span data-stu-id="1e2e3-133">x:ClassModifier Directive</span></span>](xclassmodifier-directive.md)
