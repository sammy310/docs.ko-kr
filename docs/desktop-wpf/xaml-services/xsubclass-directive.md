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
ms.openlocfilehash: e85e0fb5a0e1a865ed84a93767f8152a115bbe5f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432643"
---
# <a name="xsubclass-directive"></a><span data-ttu-id="01fc0-102">x:Subclass 지시문</span><span class="sxs-lookup"><span data-stu-id="01fc0-102">x:Subclass Directive</span></span>

<span data-ttu-id="01fc0-103">XAML 태그 컴파일 동작도 `x:Class` 제공 될 때 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-103">Modifies XAML markup compile behavior when `x:Class` is also provided.</span></span> <span data-ttu-id="01fc0-104">을 기반으로 `x:Class`하는 부분 클래스를 만드는 `x:Class` 대신 제공된 클래스가 중간 클래스로 만들어지고 제공된 파생 클래스가 을 기반으로 `x:Class`할 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-104">Instead of creating a partial class that is based on `x:Class`, the provided `x:Class` is created as an intermediate class, and then your provided derived class is expected to be based on `x:Class`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="01fc0-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="01fc0-105">XAML Attribute Usage</span></span>

```xaml
<object x:Class="namespace.classname" x:Subclass="subclassNamespace.subclassName">
   ...
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="01fc0-106">XAML 값</span><span class="sxs-lookup"><span data-stu-id="01fc0-106">XAML Values</span></span>

|||
|-|-|
|`namespace`|<span data-ttu-id="01fc0-107">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="01fc0-107">Optional.</span></span> <span data-ttu-id="01fc0-108">을 포함하는 CLR 네임스페이스를 지정합니다. `classname`</span><span class="sxs-lookup"><span data-stu-id="01fc0-108">Specifies a CLR namespace that contains `classname`.</span></span> <span data-ttu-id="01fc0-109">`namespace` 지정하면 점(.)이 `namespace` 분리되고 `classname`.</span><span class="sxs-lookup"><span data-stu-id="01fc0-109">If `namespace` is specified, a dot (.) separates `namespace` and `classname`.</span></span>|
|`classname`|<span data-ttu-id="01fc0-110">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-110">Required.</span></span> <span data-ttu-id="01fc0-111">로드된 XAML및 해당 XAML에 대한 코드 숨미를 연결하는 부분 클래스의 CLR 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-111">Specifies the CLR name of the partial class that connects the loaded XAML and your code-behind for that XAML.</span></span> <span data-ttu-id="01fc0-112">설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01fc0-112">See Remarks.</span></span>|
|`subclassNamespace`|<span data-ttu-id="01fc0-113">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="01fc0-113">Optional.</span></span> <span data-ttu-id="01fc0-114">각 네임스페이스가 `namespace` 다른 네임스페이스를 해결할 수 있는 경우와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-114">Can be different from `namespace` if each namespace can resolve the other.</span></span> <span data-ttu-id="01fc0-115">을 포함하는 CLR 네임스페이스를 지정합니다. `subclassName`</span><span class="sxs-lookup"><span data-stu-id="01fc0-115">Specifies a CLR namespace that contains `subclassName`.</span></span> <span data-ttu-id="01fc0-116">`subclassName` 지정하면 점(.)이 `subclassNamespace` 분리되고 `subclassName`.</span><span class="sxs-lookup"><span data-stu-id="01fc0-116">If `subclassName` is specified, a dot (.) separates `subclassNamespace` and `subclassName`.</span></span>|
|`subclassName`|<span data-ttu-id="01fc0-117">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-117">Required.</span></span> <span data-ttu-id="01fc0-118">하위 클래스의 CLR 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-118">Specifies the CLR name of the subclass.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="01fc0-119">종속성</span><span class="sxs-lookup"><span data-stu-id="01fc0-119">Dependencies</span></span>

<span data-ttu-id="01fc0-120">[x:Class 지시문도](xclass-directive.md) 동일한 개체에 제공되어야 하며 해당 개체는 XAML 프로덕션의 루트 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-120">[x:Class Directive](xclass-directive.md) must also be provided on the same object, and that object must be the root element of the XAML production.</span></span>

## <a name="remarks"></a><span data-ttu-id="01fc0-121">설명</span><span class="sxs-lookup"><span data-stu-id="01fc0-121">Remarks</span></span>

<span data-ttu-id="01fc0-122">`x:Subclass`사용은 주로 부분 클래스 선언을 지원하지 않는 언어를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-122">`x:Subclass` usage is primarily intended for languages that do not support partial class declarations.</span></span>

<span data-ttu-id="01fc0-123">중첩 된 `x:Subclass` 클래스로 사용되는 클래스는 `x:Subclass` 중첩 된 클래스가 될 수 없으며 "종속성" 절에 설명된 루트 개체를 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-123">The class used as the `x:Subclass` cannot be a nested class, and `x:Subclass` must refer to the root object as explained in the "Dependencies" section.</span></span>

<span data-ttu-id="01fc0-124">그렇지 않으면 .NET XAML 서비스 구현에서 개념적 의미를 `x:Subclass` 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-124">Otherwise, the conceptual meaning of `x:Subclass` is undefined by a .NET XAML Services implementation.</span></span> <span data-ttu-id="01fc0-125">이는 .NET XAML 서비스 동작이 XAML 태그 및 백업 코드가 연결된 전체 프로그래밍 모델을 지정하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-125">This is because .NET XAML Services behavior does not specify the overall programming model by which XAML markup and backing code are connected.</span></span> <span data-ttu-id="01fc0-126">XAML 태그, 컴파일된 태그 및 CLR 기반 코드 숨결을 연결하는 방법을 정의하기 위해 프로그래밍 모델 또는 응용 프로그램 모델을 사용하는 특정 프레임워크와 `x:Class` 관련및 `x:Subclass` 수행되는 추가 개념의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-126">Implementations of further concepts related to `x:Class` and `x:Subclass` are performed by specific frameworks that use programming models or application models to define how to connect XAML markup, compiled markup, and CLR-based code-behind.</span></span> <span data-ttu-id="01fc0-127">각 프레임워크에는 일부 동작을 사용하도록 설정하는 자체 빌드 작업 또는 빌드 환경에 포함되어야 하는 특정 구성 요소가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-127">Each framework might have its own build actions that enable some of the behavior, or specific components that must be included in the build environment.</span></span> <span data-ttu-id="01fc0-128">프레임워크 내에서 빌드 작업은 코드 숨결에 사용되는 특정 CLR 언어에 따라 달라질 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-128">Within a framework, build actions can also vary based on the specific CLR language that is used for the code-behind.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="01fc0-129">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="01fc0-129">WPF Usage Notes</span></span>

<span data-ttu-id="01fc0-130">`x:Subclass`이미 있는 응용 프로그램 정의의 <xref:System.Windows.Application> 페이지 루트 또는 루트에 있을 수 있습니다. `x:Class`</span><span class="sxs-lookup"><span data-stu-id="01fc0-130">`x:Subclass` can be on a page root or on the <xref:System.Windows.Application> root in the application definition, which already has `x:Class`.</span></span> <span data-ttu-id="01fc0-131">`x:Subclass` 페이지 또는 응용 프로그램 루트 이외의 모든 요소를 선언하거나 `x:Class` 존재하지 않는 곳에 지정하면 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-131">Declaring `x:Subclass` on any element other than a page or application root, or specifying it where no `x:Class` exists, causes a compile-time error.</span></span>

<span data-ttu-id="01fc0-132">시나리오에 대해 올바르게 작동하는 `x:Subclass` 파생 클래스를 만드는 것은 상당히 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-132">Creating derived classes that work correctly for the `x:Subclass` scenario is fairly complex.</span></span> <span data-ttu-id="01fc0-133">중간 파일(.xaml 파일 이름을 통합한 이름으로 태그 컴파일을 통해 프로젝트의 obj 폴더에서 생성된 .g 파일)을 검사해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-133">You might need to examine the intermediate files (the .g files produced in the obj folder of your project by markup compile, with names that incorporate the .xaml file names).</span></span> <span data-ttu-id="01fc0-134">이러한 중간 파일은 컴파일된 응용 프로그램의 조인된 부분 클래스에서 특정 프로그래밍 구문의 출처를 확인하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-134">These intermediate files can help you determine the origin of certain programming constructs in the joined partial classes in the compiled application.</span></span>

<span data-ttu-id="01fc0-135">파생 클래스의 이벤트 처리기는 `internal override` `Friend Overrides` 컴파일 하는 동안 중간 클래스에서 만든 처리기의 스텁을 재정의하기 위해 (Microsoft Visual Basic)이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-135">Event handlers in the derived class must be `internal override` (`Friend Overrides` in Microsoft Visual Basic) in order to override the stubs for the handlers as created in the intermediate class during compilation.</span></span> <span data-ttu-id="01fc0-136">그렇지 않으면 파생된 클래스 구현은 중간 클래스 구현을 숨기거나(shadow) 되고 중간 클래스 처리기는 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-136">Otherwise, the derived class implementations hide (shadow) the intermediate class implementation and the intermediate class handlers are not invoked.</span></span>

<span data-ttu-id="01fc0-137">을 모두 `x:Class` `x:Subclass`정의할 때 `x:Class`에서 참조하는 클래스에 대한 구현을 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-137">When you define both `x:Class` and `x:Subclass`, you do not need to provide any implementation for the class that is referenced by `x:Class`.</span></span> <span data-ttu-id="01fc0-138">컴파일러가 중간 파일에서 만드는 `x:Class` 클래스에 대한 몇 가지 지침을 가지도록 특성을 통해 이름을 지정하면 됩니다(컴파일러는 이 경우 기본 이름을 선택하지 않음).</span><span class="sxs-lookup"><span data-stu-id="01fc0-138">You only need to give it a name via the `x:Class` attribute so that the compiler has some guidance for the class that it creates in the intermediate files (the compiler does not select a default name in this case).</span></span> <span data-ttu-id="01fc0-139">클래스에 `x:Class` 구현을 제공할 수 있습니다. 그러나 이 시나리오는 둘 다 `x:Class` 및 `x:Subclass`을 모두 사용하는 일반적인 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="01fc0-139">You can give the `x:Class` class an implementation; however, this is not the typical scenario for using both `x:Class` and `x:Subclass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="01fc0-140">참조</span><span class="sxs-lookup"><span data-stu-id="01fc0-140">See also</span></span>

- [<span data-ttu-id="01fc0-141">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="01fc0-141">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="01fc0-142">WPF에 대한 XAML 및 사용자 지정 클래스</span><span class="sxs-lookup"><span data-stu-id="01fc0-142">XAML and Custom Classes for WPF</span></span>](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
