---
title: x:Code 내장 XAML 형식
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432805"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="a4211-102">x:Code 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="a4211-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="a4211-103">XAML 프로덕션 내에서 코드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="a4211-104">이러한 코드는 XAML을 컴파일하는 모든 XAML 프로세서 구현에서 컴파일하거나 런타임에 의한 해석과 같은 나중에 사용하기 위해 XAML 프로덕션에 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a4211-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="a4211-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="a4211-106">설명</span><span class="sxs-lookup"><span data-stu-id="a4211-106">Remarks</span></span>

<span data-ttu-id="a4211-107">XAML `x:Code` 지시문 요소 내의 코드는 여전히 일반적인 XML 네임스페이스 및 제공된 XAML 네임스페이스 내에서 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="a4211-108">따라서 일반적으로 `x:Code` `CDATA` 세그먼트 내부에 사용되는 코드를 동봉해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="a4211-109">`x:Code`XAML 프로덕션의 가능한 모든 배포 메커니즘에 대해 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="a4211-110">특정 프레임워크(예: WPF)에서는 코드를 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="a4211-111">다른 프레임워크에서는 `x:Code` 일반적으로 사용이 허용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="a4211-112">관리되는 `x:Code` 콘텐츠를 허용하는 프레임워크의 경우 콘텐츠에 `x:Code` 사용할 올바른 언어 컴파일러는 응용 프로그램을 컴파일하는 데 사용되는 포함 프로젝트의 설정 및 대상에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="a4211-113">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="a4211-113">WPF Usage Notes</span></span>

<span data-ttu-id="a4211-114">WPF내에서 `x:Code` 선언된 코드에는 다음과 같은 몇 가지 주목할 만한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="a4211-115">`x:Code` 지시문 요소는 XAML 프로덕션의 루트 요소의 즉각적인 자식 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="a4211-116">[x:Class 지시문은](xclass-directive.md) 부모 루트 요소에 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="a4211-117">내에 `x:Code` 배치된 코드는 컴파일에 의해 해당 XAML 페이지에 대해 이미 생성중인 부분 클래스의 범위 내에 있도록 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="a4211-118">따라서 정의하는 모든 코드는 해당 부분 클래스의 멤버 또는 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="a4211-119">부분 클래스 내에 클래스를 중첩하는 것 외에는 추가 클래스를 정의할 수 없습니다(중첩은 허용되지만 XAML에서 중첩된 클래스를 참조할 수 없기 때문에 일반적이지는 않습니다).</span><span class="sxs-lookup"><span data-stu-id="a4211-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="a4211-120">기존 부분 클래스에 사용되는 네임스페이스 이외의 CLR 네임스페이스는 정의하거나 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="a4211-121">부분 클래스 CLR 네임스페이스 외부의 코드 엔터티에 대한 참조는 모두 정규화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="a4211-122">선언되는 멤버가 부분 클래스 재정의 가능한 멤버에 재정의되는 경우 언어별 재정의 키워드로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="a4211-123">XAML에서 `x:Code` 만든 부분 클래스의 멤버와 범위 충돌에서 선언된 멤버가 컴파일러가 충돌을 보고하는 방식으로 XAML 파일을 컴파일하거나 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4211-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4211-124">참조</span><span class="sxs-lookup"><span data-stu-id="a4211-124">See also</span></span>

- [<span data-ttu-id="a4211-125">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="a4211-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="a4211-126">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="a4211-126">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="a4211-127">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="a4211-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
