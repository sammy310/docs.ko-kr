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
ms.openlocfilehash: ea7bc17cba19137b4e4ca2d8cddb32e6630887c9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544845"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="1ed2f-102">x:Code 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="1ed2f-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="1ed2f-103">XAML 프로덕션 내에서 코드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="1ed2f-104">이러한 코드는 xaml을 컴파일하는 XAML 프로세서 구현에 의해 컴파일하거나 나중에 런타임에의 한 해석을 위해 XAML 프로덕션에 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="1ed2f-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="1ed2f-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="1ed2f-106">설명</span><span class="sxs-lookup"><span data-stu-id="1ed2f-106">Remarks</span></span>

<span data-ttu-id="1ed2f-107">`x:Code`Xaml 지시문 요소 내의 코드는 여전히 일반 XML 네임 스페이스 및 제공 된 xaml 네임 스페이스 내에서 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="1ed2f-108">따라서 일반적으로 세그먼트 내부에 사용 되는 코드를 묶어야 `x:Code` `CDATA` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="1ed2f-109">`x:Code` 는 XAML 프로덕션의 모든 가능한 배포 메커니즘에 대해 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="1ed2f-110">특정 프레임 워크 (예: WPF)에서 코드를 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="1ed2f-111">다른 프레임 워크에서는 `x:Code` 일반적으로 사용이 허용 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="1ed2f-112">관리 되는 콘텐츠를 허용 하는 프레임 워크의 경우 `x:Code` 콘텐츠에 사용할 올바른 언어 컴파일러는 `x:Code` 응용 프로그램을 컴파일하는 데 사용 되는 포함 하는 프로젝트의 설정 및 대상에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="1ed2f-113">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="1ed2f-113">WPF Usage Notes</span></span>

<span data-ttu-id="1ed2f-114">WPF 용 내에 선언 `x:Code` 된 코드에는 몇 가지 주목할 만한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="1ed2f-115">`x:Code`지시문 요소는 XAML 프로덕션의 루트 요소에 대 한 직계 자식 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="1ed2f-116">[X:Class 지시문](xclass-directive.md) 은 부모 루트 요소에 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="1ed2f-117">내에 배치 된 코드는 `x:Code` 해당 XAML 페이지에 대해 이미 만들어진 partial 클래스의 범위 내에 있도록 컴파일에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="1ed2f-118">따라서 사용자가 정의 하는 모든 코드는 해당 partial 클래스의 멤버 또는 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="1ed2f-119">Partial 클래스 내에 클래스를 중첩 하는 것 외에는 추가 클래스를 정의할 수 없습니다. 중첩은 허용 되지만 XAML에서 중첩 된 클래스를 참조할 수 없기 때문에 일반적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="1ed2f-120">기존 partial 클래스에 사용 되는 네임 스페이스가 아닌 CLR 네임 스페이스는 정의 하거나에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="1ed2f-121">Partial class CLR 네임 스페이스 외부에 있는 코드 엔터티에 대 한 참조는 모두 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="1ed2f-122">선언 되는 멤버가 partial 클래스 재정의 가능한 멤버에 대 한 재정의 인 경우 언어별 override 키워드를 사용 하 여이를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="1ed2f-123">범위에 선언 된 멤버가 `x:Code` XAML에서 생성 된 partial 클래스의 멤버와 충돌 하는 경우, 컴파일러에서 충돌을 보고 하는 경우 xaml 파일을 컴파일하거나 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed2f-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ed2f-124">참조</span><span class="sxs-lookup"><span data-stu-id="1ed2f-124">See also</span></span>

- [<span data-ttu-id="1ed2f-125">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="1ed2f-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="1ed2f-126">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="1ed2f-126">Code-Behind and XAML in WPF</span></span>](/dotnet/desktop/wpf/advanced/code-behind-and-xaml-in-wpf)
- [<span data-ttu-id="1ed2f-127">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="1ed2f-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
