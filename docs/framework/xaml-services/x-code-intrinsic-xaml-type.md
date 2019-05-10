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
ms.openlocfilehash: f6898008fa3e3e7e385a2bc77c5b2eac7eeda2ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617150"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="6ae11-102">x:Code 내장 XAML 형식</span><span class="sxs-lookup"><span data-stu-id="6ae11-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="6ae11-103">XAML 프로덕션 내에서 코드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="6ae11-104">이러한 코드 XAML, 또는 런타임에 의해 해석 등 사용에 대 한 XAML 프로덕션의 왼쪽을 컴파일되지 않는 XAML 프로세서 구현 하 여 컴파일될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="6ae11-105">XAML 개체 요소 사용</span><span class="sxs-lookup"><span data-stu-id="6ae11-105">XAML Object Element Usage</span></span>  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a><span data-ttu-id="6ae11-106">설명</span><span class="sxs-lookup"><span data-stu-id="6ae11-106">Remarks</span></span>  
 <span data-ttu-id="6ae11-107">내의 코드는 `x:Code` XAML 지시문 요소는 여전히 일반 XML 네임 스페이스 내에서 해석 및 제공 된 XAML 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="6ae11-108">에 사용 되는 코드를 포함 하는 데 일반적으로 필요한 것 이므로 `x:Code` 안에 `CDATA` 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>  
  
 <span data-ttu-id="6ae11-109">`x:Code` XAML 프로덕션의 모든 가능한 배포 메커니즘에 대해 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="6ae11-110">특정 프레임 워크 (예: WPF) 코드를 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="6ae11-111">다른 프레임 워크에서 `x:Code` 사용은 일반적으로 허용 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>  
  
 <span data-ttu-id="6ae11-112">관리 되는 허용 하는 프레임 워크 `x:Code` 콘텐츠를에 사용할 언어 컴파일러 `x:Code` 콘텐츠 설정 및 응용 프로그램을 컴파일하는 데 사용 되는 포함 하는 프로젝트의 대상에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="6ae11-113">WPF 사용 정보</span><span class="sxs-lookup"><span data-stu-id="6ae11-113">WPF Usage Notes</span></span>  
 <span data-ttu-id="6ae11-114">코드 내에서 선언 된 `x:Code` WPF에 몇 가지 주목할 만한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>  
  
- <span data-ttu-id="6ae11-115">`x:Code` 지시문 요소는 XAML 프로덕션의 루트 요소의 직계 자식 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>  
  
- <span data-ttu-id="6ae11-116">[X:class 지시문](x-class-directive.md) 부모 root 요소에서 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-116">[x:Class Directive](x-class-directive.md) must be provided on the parent root element.</span></span>  
  
- <span data-ttu-id="6ae11-117">코드 내에 배치 `x:Code` 만들어지는 이미 해당 XAML 페이지에 대 한 partial 클래스의 범위 내에 있는 컴파일 작업으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="6ae11-118">따라서 정의한 모든 코드는 partial 클래스의 멤버 또는 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-118">Therefore all code you define must be members or variables of that partial class.</span></span>  
  
- <span data-ttu-id="6ae11-119">Partial 클래스 내에 클래스를 중첩 하는 대신 추가 클래스를 정의할 수 없습니다 (중첩 허용 되지만 아니므로 일반적인 XAML에서 중첩된 클래스를 참조할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="6ae11-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="6ae11-120">기존 partial 클래스에 사용 되는 네임 스페이스 이외의 CLR 네임 스페이스를 정의 하거나 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>  
  
- <span data-ttu-id="6ae11-121">Partial 클래스 CLR 네임 스페이스 외부 코드 엔터티에 대 한 참조는 모두 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="6ae11-122">멤버 선언 되는 부분 클래스 재정의 가능한 멤버에 대 한 재정의 경우이 언어별 override 키워드를 사용 하 여 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="6ae11-123">멤버에 선언 된 경우 `x:Code` 범위는 XAML에서 생성 된 partial 클래스의 멤버와 충돌, 이러한 방식으로 컴파일러에서 충돌을 보고 하는 XAML 파일 컴파일 없거나 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ae11-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae11-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ae11-124">See also</span></span>

- [<span data-ttu-id="6ae11-125">x:Class 지시문</span><span class="sxs-lookup"><span data-stu-id="6ae11-125">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="6ae11-126">WPF의 코드 숨김 및 XAML</span><span class="sxs-lookup"><span data-stu-id="6ae11-126">Code-Behind and XAML in WPF</span></span>](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="6ae11-127">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="6ae11-127">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
