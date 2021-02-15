---
description: '자세한 정보: 같음 연산자'
title: 같음 연산자
ms.date: 10/22/2008
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 8678ed1b4bc320f685cf7ae172f064b3dededd04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642242"
---
# <a name="equality-operators"></a><span data-ttu-id="3dc29-103">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="3dc29-103">Equality Operators</span></span>

<span data-ttu-id="3dc29-104">이 섹션에서는 같음 연산자 오버로드에 대해 설명하고 `operator==` 및 `operator!=`를 같음 연산자로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-104">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>

 <span data-ttu-id="3dc29-105">❌ 같음 연산자 중 하나를 오버로드하지 않고 다른 연산자를 오버로드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="3dc29-105">❌ DO NOT overload one of the equality operators and not the other.</span></span>

 <span data-ttu-id="3dc29-106">✔️ <xref:System.Object.Equals%2A?displayProperty=nameWithType> 및 같음 연산자가 정확하게 동일한 의미 체계 및 유사한 성능 특성을 갖는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc29-106">✔️ DO ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>

 <span data-ttu-id="3dc29-107">즉, 같음 연산자를 오버로드할 때 `Object.Equals`를 재정의해야 함을 의미하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-107">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>

 <span data-ttu-id="3dc29-108">❌ 같음 연산자에서 예외를 throw하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-108">❌ AVOID throwing exceptions from equality operators.</span></span>

 <span data-ttu-id="3dc29-109">예를 들어 인수 중 하나가 null인 경우 `NullReferenceException`을 throw하는 대신 false를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-109">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>

## <a name="equality-operators-on-value-types"></a><span data-ttu-id="3dc29-110">값 형식의 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="3dc29-110">Equality Operators on Value Types</span></span>

 <span data-ttu-id="3dc29-111">✔️ 같음이 의미가 있는 경우 값 형식에서 같음 연산자를 오버로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3dc29-111">✔️ DO overload the equality operators on value types, if equality is meaningful.</span></span>

 <span data-ttu-id="3dc29-112">대부분의 프로그래밍 언어에는 값 형식에 대한 `operator==`의 기본 구현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-112">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>

## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="3dc29-113">참조 형식의 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="3dc29-113">Equality Operators on Reference Types</span></span>

 <span data-ttu-id="3dc29-114">❌ 변경 가능한 참조 형식에서 같음 연산자를 오버로드하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-114">❌ AVOID overloading equality operators on mutable reference types.</span></span>

 <span data-ttu-id="3dc29-115">많은 언어에는 참조 형식에 대한 기본 제공 같음 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-115">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="3dc29-116">기본 제공 연산자는 일반적으로 참조 같음을 구현하며, 기본 동작이 값 같음으로 변경될 때 많은 개발자가 놀랍니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-116">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>

 <span data-ttu-id="3dc29-117">불변성으로 인해 참조 같음과 값 같음 간의 차이를 알아차리기가 훨씬 더 어렵기 때문에 변경 불가능한 참조 형식에서는 이 문제가 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-117">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>

 <span data-ttu-id="3dc29-118">❌ 구현 속도가 참조 같음의 구현보다 현저하게 느린 경우 참조 형식에서 같음 연산자를 오버로드하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dc29-118">❌ AVOID overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>

 <span data-ttu-id="3dc29-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="3dc29-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="3dc29-120">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="3dc29-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="3dc29-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dc29-121">See also</span></span>

- [<span data-ttu-id="3dc29-122">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="3dc29-122">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="3dc29-123">사용 지침</span><span class="sxs-lookup"><span data-stu-id="3dc29-123">Usage Guidelines</span></span>](usage-guidelines.md)
