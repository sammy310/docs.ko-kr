---
title: 멤버 오버로드
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: 4caa0ae78d168b23fd2862153bef0e3960d3ea42
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392951"
---
# <a name="member-overloading"></a><span data-ttu-id="4da48-102">멤버 오버로드</span><span class="sxs-lookup"><span data-stu-id="4da48-102">Member Overloading</span></span>
<span data-ttu-id="4da48-103">멤버 오버 로드는 매개 변수의 개수나 형식만 다르고 이름이 동일한 동일한 형식으로 둘 이상의 멤버를 만드는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-103">Member overloading means creating two or more members on the same type that differ only in the number or type of parameters but have the same name.</span></span> <span data-ttu-id="4da48-104">예를 들어, 다음에서 `WriteLine` 메서드는 오버 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-104">For example, in the following, the `WriteLine` method is overloaded:</span></span>  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 <span data-ttu-id="4da48-105">메서드, 생성자 및 인덱싱된 속성만 매개 변수를 가질 수 있으므로 해당 멤버만 오버 로드 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-105">Because only methods, constructors, and indexed properties can have parameters, only those members can be overloaded.</span></span>  
  
 <span data-ttu-id="4da48-106">오버 로드는 유용성, 생산성 및 재사용 가능한 라이브러리의 가독성을 향상 시키기 위한 가장 중요 한 기술 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-106">Overloading is one of the most important techniques for improving usability, productivity, and readability of reusable libraries.</span></span> <span data-ttu-id="4da48-107">매개 변수 수를 오버 로드 하면 더 간단한 버전의 생성자와 메서드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-107">Overloading on the number of parameters makes it possible to provide simpler versions of constructors and methods.</span></span> <span data-ttu-id="4da48-108">매개 변수 형식에 대 한 오버 로드를 사용 하면 선택한 다른 형식 집합에 대해 동일한 작업을 수행 하는 멤버에 대해 동일한 멤버 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-108">Overloading on the parameter type makes it possible to use the same member name for members performing identical operations on a selected set of different types.</span></span>  
  
 <span data-ttu-id="4da48-109">**✓ DO** 짧은 오버 로드에서 사용 되는 기본값을 나타내기 위해 설명 매개 변수 이름을 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-109">**✓ DO** try to use descriptive parameter names to indicate the default used by shorter overloads.</span></span>  
  
 <span data-ttu-id="4da48-110">**X AVOID** 임의의 여러 오버 로드에 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-110">**X AVOID** arbitrarily varying parameter names in overloads.</span></span> <span data-ttu-id="4da48-111">한 오버 로드의 매개 변수가 다른 오버 로드의 매개 변수와 동일한 입력을 나타내는 경우 매개 변수의 이름이 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-111">If a parameter in one overload represents the same input as a parameter in another overload, the parameters should have the same name.</span></span>  
  
 <span data-ttu-id="4da48-112">**X AVOID** 오버 로드 된 멤버의 매개 변수 순서에 일관 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-112">**X AVOID** being inconsistent in the ordering of parameters in overloaded members.</span></span> <span data-ttu-id="4da48-113">이름이 같은 매개 변수는 모든 오버 로드에서 동일한 위치에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-113">Parameters with the same name should appear in the same position in all overloads.</span></span>  
  
 <span data-ttu-id="4da48-114">**✓ DO** (확장 기능이 필요) 하는 경우 가상 가장 긴 오버 로드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-114">**✓ DO** make only the longest overload virtual (if extensibility is required).</span></span> <span data-ttu-id="4da48-115">짧은 오버 로드는 단순히를 통해 보다 긴 오버 로드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-115">Shorter overloads should simply call through to a longer overload.</span></span>  
  
 <span data-ttu-id="4da48-116">**X DO NOT** 사용 `ref` 또는 `out` 한정자를 멤버를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-116">**X DO NOT** use `ref` or `out` modifiers to overload members.</span></span>  
  
 <span data-ttu-id="4da48-117">일부 언어에서는 다음과 같은 오버 로드에 대 한 호출을 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-117">Some languages cannot resolve calls to overloads like this.</span></span> <span data-ttu-id="4da48-118">또한 이러한 오버 로드는 일반적으로 완전히 다른 의미 체계를 가지 며 오버 로드를 제외 하 고 별도의 두 메서드를 대신 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-118">In addition, such overloads usually have completely different semantics and probably should not be overloads but two separate methods instead.</span></span>  
  
 <span data-ttu-id="4da48-119">**X DO NOT** 서로 다른 의미 체계 하면서도 동일한 위치와 유사한 형식 매개 변수를 사용 하는 오버 로드를 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-119">**X DO NOT** have overloads with parameters at the same position and similar types yet with different semantics.</span></span>  
  
 <span data-ttu-id="4da48-120">**✓ DO** 허용 `null` 선택적 인수를 전달 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-120">**✓ DO**  allow `null` to be passed for optional arguments.</span></span>  
  
 <span data-ttu-id="4da48-121">**✓ DO** 멤버 기본 인수가 있는 멤버를 정의 하는 대신 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-121">**✓ DO** use member overloading rather than defining members with default arguments.</span></span>  
  
 <span data-ttu-id="4da48-122">기본 인수는 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4da48-122">Default arguments are not CLS compliant.</span></span>  
  
 <span data-ttu-id="4da48-123">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="4da48-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="4da48-124">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="4da48-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da48-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4da48-125">See also</span></span>

- [<span data-ttu-id="4da48-126">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4da48-126">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="4da48-127">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="4da48-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
