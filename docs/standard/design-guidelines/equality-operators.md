---
title: 같음 연산자
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 2331a852adb4dd254af85060a5077f454bcfe0eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734428"
---
# <a name="equality-operators"></a><span data-ttu-id="aa519-102">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="aa519-102">Equality Operators</span></span>

<span data-ttu-id="aa519-103">이 섹션에서는 같음 연산자를 오버 로드 하 고 같음 연산자를 참조 하는 방법을 설명 `operator==` `operator!=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="aa519-104">❌ 같음 연산자 중 하나를 오버 로드 하지 않고 다른 연산자를 오버 로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-104">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="aa519-105"><xref:System.Object.Equals%2A?displayProperty=nameWithType>및 같음 연산자에 정확히 동일한 의미 체계와 유사한 성능 특성이 있는지 확인 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-105">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="aa519-106">이는 `Object.Equals` 같음 연산자가 오버 로드 될 때를 재정의 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="aa519-107">❌ 같음 연산자에서 예외가 throw 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-107">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="aa519-108">예를 들어 인수 중 하나가 null이 아닌 null 이면 false를 반환 `NullReferenceException` 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="aa519-109">값 형식에 대 한 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="aa519-109">Equality Operators on Value Types</span></span>

 <span data-ttu-id="aa519-110">같음 값이 의미 하는 경우 값 형식에 대 한 같음 연산자를 오버 로드 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-110">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="aa519-111">대부분의 프로그래밍 언어에는 `operator==` 값 형식에 대 한 기본 구현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="aa519-112">참조 형식에 대 한 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="aa519-112">Equality Operators on Reference Types</span></span>

 <span data-ttu-id="aa519-113">❌ 변경 가능한 참조 형식에 대해 같음 연산자를 오버 로드 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="aa519-113">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="aa519-114">많은 언어에는 참조 형식에 대 한 같음 연산자가 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="aa519-115">기본 제공 연산자는 일반적으로 참조 같음을 구현 하며, 대부분의 개발자는 기본 동작이 값 같음으로 변경 될 때 많은 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="aa519-116">불변성은 참조 같음 및 값 같음 간의 차이를 보다 쉽게 알 수 있으므로이 문제는 변경할 수 없는 참조 형식에 대해 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa519-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="aa519-117">❌ 구현이 참조가 일치 하는 것 보다 훨씬 느린 경우 참조 형식에 대해 같음 연산자를 오버 로드 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="aa519-117">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="aa519-118">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="aa519-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="aa519-119">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="aa519-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="aa519-120">참조</span><span class="sxs-lookup"><span data-stu-id="aa519-120">See also</span></span>

- [<span data-ttu-id="aa519-121">프레임 워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="aa519-121">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="aa519-122">사용 지침</span><span class="sxs-lookup"><span data-stu-id="aa519-122">Usage Guidelines</span></span>](usage-guidelines.md)
