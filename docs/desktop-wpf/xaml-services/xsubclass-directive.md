---
title: x:Subclass 지시문
ms.date: 03/30/2017
f1_keywords:
- Subclass
- xSubclass
- x:Subclass
helpviewer_keywords:
- x:Subclass attribute [XAML Services]
- XAML [XAML Services], x:Subclass attribute
- Subclass attribute in XAML [XAML Services]
ms.assetid: 99f66072-8107-4362-ab99-8171dc83b469
ms.openlocfilehash: b888ef73d1678fd37c984e4bb223f24e5b65d2cc
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540721"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="83c0f-102">x:Subclass 지시문</span><span class="sxs-lookup"><span data-stu-id="83c0f-102">x:Subclass Directive</span></span>

<span data-ttu-id="83c0f-103">가 제공 될 때 XAML 태그 컴파일 동작 `x:Class` 을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="83c0f-104">을 기반으로 하는 partial 클래스를 만드는 대신 `x:Class` 제공 된 `x:Class` 가 중간 클래스로 생성 된 다음 제공 된 파생 클래스의 기반이 될 것으로 예상 됩니다 `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="83c0f-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="83c0f-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="83c0f-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="83c0f-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="83c0f-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="83c0f-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-107">Optional.</span></span> <span data-ttu-id="83c0f-108">가 포함 된 CLR 네임 스페이스를 지정 합니다 `classname` .</span><span class="sxs-lookup"><span data-stu-id="83c0f-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="83c0f-109">을 `namespace` 지정 하면 점 (.)은 및를 `namespace` 구분 `classname` 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="83c0f-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="83c0f-110">Required.</span></span> <span data-ttu-id="83c0f-111">해당 XAML에 대해 로드 된 XAML 및 코드 숨김이 연결 되는 partial 클래스의 CLR 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="83c0f-112">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83c0f-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="83c0f-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-113">Optional.</span></span> <span data-ttu-id="83c0f-114">`namespace`각 네임 스페이스에서 다른를 확인할 수 있는 경우와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="83c0f-115">가 포함 된 CLR 네임 스페이스를 지정 합니다 `subclassName` .</span><span class="sxs-lookup"><span data-stu-id="83c0f-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="83c0f-116">을 `subclassName` 지정 하면 점 (.)은 및를 `subclassNamespace` 구분 `subclassName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="83c0f-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="83c0f-117">Required.</span></span> <span data-ttu-id="83c0f-118">서브 클래스의 CLR 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="83c0f-119">종속성</span><span class="sxs-lookup"><span data-stu-id="83c0f-119">Dependencies</span></span>

<span data-ttu-id="83c0f-120">[X:Class 지시문](xclass-directive.md) 도 동일한 개체에서 제공 해야 하며, 해당 개체는 XAML 프로덕션의 루트 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="83c0f-121">설명</span><span class="sxs-lookup"><span data-stu-id="83c0f-121">Remarks</span></span>

<span data-ttu-id="83c0f-122">`x:Subclass` 사용은 주로 partial 클래스 선언을 지원 하지 않는 언어를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="83c0f-123">로 사용 되는 클래스는 `x:Subclass` 중첩 된 클래스가 될 수 없으며 `x:Subclass` "종속성" 섹션에 설명 된 대로 루트 개체를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="83c0f-124">그렇지 않은 경우의 개념 의미는 `x:Subclass` .NET XAML 서비스 구현에서 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="83c0f-125">.NET XAML 서비스 동작은 XAML 태그 및 백업 코드가 연결 되는 전체 프로그래밍 모델을 지정 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="83c0f-126">및와 관련 된 추가 개념의 구현은 `x:Class` `x:Subclass` XAML 태그, 컴파일된 태그 및 CLR 기반 코드를 연결 하는 방법을 정의 하기 위해 프로그래밍 모델 또는 응용 프로그램 모델을 사용 하는 특정 프레임 워크에 의해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="83c0f-127">각 프레임 워크에는 일부 동작이 나 빌드 환경에 포함 되어야 하는 특정 구성 요소를 사용할 수 있도록 하는 고유한 빌드 작업이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="83c0f-128">프레임 워크 내에서 빌드 작업은 코드 숨김으로 사용 되는 특정 CLR 언어에 따라 달라질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="83c0f-129">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="83c0f-129">WPF Usage Notes</span></span>

<span data-ttu-id="83c0f-130">`x:Subclass` 는 <xref:System.Windows.Application> 이미 있는 응용 프로그램 정의의 루트 또는 페이지 루트에 있을 수 있습니다 `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="83c0f-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="83c0f-131">`x:Subclass`페이지나 응용 프로그램 루트 이외의 요소에 선언 하거나 존재 하지 않는 요소를 지정 하면 `x:Class` 컴파일 시간 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="83c0f-132">시나리오에서 제대로 작동 하는 파생 클래스를 만드는 `x:Subclass` 것은 매우 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="83c0f-133">.Xaml 파일 이름을 포함 하는 이름을 사용 하 여 태그 컴파일로 프로젝트의 obj 폴더에 생성 된 중간 파일 (. g 파일)을 검사 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="83c0f-134">이러한 중간 파일은 컴파일된 응용 프로그램에서 조인 된 partial 클래스의 특정 프로그래밍 구문에 대 한 원본을 결정 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="83c0f-135">`internal override` `Friend Overrides` 컴파일 중에 중간 클래스에서 만든 처리기의 스텁을 재정의 하려면 파생 클래스의 이벤트 처리기가 (Microsoft Visual Basic) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="83c0f-136">그렇지 않으면 파생 클래스 구현에서 중간 클래스 구현을 숨기고 중간 클래스 처리기가 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="83c0f-137">및를 둘 다 정의 하는 경우 `x:Class` `x:Subclass` 에서 참조 하는 클래스에 대 한 구현을 제공할 필요가 없습니다 `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="83c0f-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="83c0f-138">`x:Class`컴파일러가 중간 파일에 만드는 클래스에 대 한 몇 가지 지침을 포함 하도록 특성을 통해 이름을 지정 하기만 하면 됩니다. 컴파일러는이 경우 기본 이름을 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83c0f-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="83c0f-139">클래스에 구현을 제공할 수 있지만 `x:Class` 및를 모두 사용 하는 일반적인 시나리오는 아닙니다. `x:Class` `x:Subclass`</span><span class="sxs-lookup"><span data-stu-id="83c0f-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="83c0f-140">참조</span><span class="sxs-lookup"><span data-stu-id="83c0f-140">See also</span></span>

- [<span data-ttu-id="83c0f-141">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="83c0f-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="83c0f-142">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="83c0f-142">XAML and Custom Classes for WPF</span></span>](/dotnet/desktop/wpf/advanced/xaml-and-custom-classes-for-wpf)
