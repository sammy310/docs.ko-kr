---
title: 같음 연산자
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 31a5ce18f4526b5e3b8411365dff812601de87ad
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709441"
---
# <a name="equality-operators"></a><span data-ttu-id="e0958-102">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="e0958-102">Equality Operators</span></span>
<span data-ttu-id="e0958-103">이 섹션에서는 같음 연산자를 오버 로드 하는 방법을 설명 하 고 같음 연산자로 `operator==` 및 `operator!=`을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-103">This section discusses overloading equality operators and refers to `operator==` and `operator!=` as equality operators.</span></span>  
  
 <span data-ttu-id="e0958-104">**X DO NOT** 같음 연산자 있고 다른 선언 중 하나를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-104">**X DO NOT** overload one of the equality operators and not the other.</span></span>  
  
 <span data-ttu-id="e0958-105">**✓ DO** 되도록 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 및 같음 연산자는 정확히 동일한 의미 체계와 비슷한 성능 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-105">**✓ DO** ensure that <xref:System.Object.Equals%2A?displayProperty=nameWithType> and the equality operators have exactly the same semantics and similar performance characteristics.</span></span>  
  
 <span data-ttu-id="e0958-106">이것은 같음 연산자가 오버 로드 될 때 `Object.Equals`를 재정의 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-106">This often means that `Object.Equals` needs to be overridden when the equality operators are overloaded.</span></span>  
  
 <span data-ttu-id="e0958-107">**X AVOID** 같음 연산자에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-107">**X AVOID** throwing exceptions from equality operators.</span></span>  
  
 <span data-ttu-id="e0958-108">예를 들어 `NullReferenceException`를 throw 하는 대신 인수 중 하나가 null 이면 false를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-108">For example, return false if one of the arguments is null instead of throwing `NullReferenceException`.</span></span>  
  
## <a name="equality-operators-on-value-types"></a><span data-ttu-id="e0958-109">값 형식에 대 한 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="e0958-109">Equality Operators on Value Types</span></span>  
 <span data-ttu-id="e0958-110">**✓ DO** 같음이 의미가 있을 경우에 값 형식에 같음 연산자를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-110">**✓ DO** overload the equality operators on value types, if equality is meaningful.</span></span>  
  
 <span data-ttu-id="e0958-111">대부분의 프로그래밍 언어에는 값 형식에 대 한 `operator==`의 기본 구현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-111">In most programming languages, there is no default implementation of `operator==` for value types.</span></span>  
  
## <a name="equality-operators-on-reference-types"></a><span data-ttu-id="e0958-112">참조 형식에 대 한 같음 연산자</span><span class="sxs-lookup"><span data-stu-id="e0958-112">Equality Operators on Reference Types</span></span>  
 <span data-ttu-id="e0958-113">**X AVOID** 변경 가능한 참조 형식에 같음 연산자를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-113">**X AVOID** overloading equality operators on mutable reference types.</span></span>  
  
 <span data-ttu-id="e0958-114">많은 언어에는 참조 형식에 대 한 같음 연산자가 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-114">Many languages have built-in equality operators for reference types.</span></span> <span data-ttu-id="e0958-115">기본 제공 연산자는 일반적으로 참조 같음을 구현 하며, 대부분의 개발자는 기본 동작이 값 같음으로 변경 될 때 많은 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-115">The built-in operators usually implement the reference equality, and many developers are surprised when the default behavior is changed to the value equality.</span></span>  
  
 <span data-ttu-id="e0958-116">불변성은 참조 같음 및 값 같음 간의 차이를 보다 쉽게 알 수 있으므로이 문제는 변경할 수 없는 참조 형식에 대해 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-116">This problem is mitigated for immutable reference types because immutability makes it much harder to notice the difference between reference equality and value equality.</span></span>  
  
 <span data-ttu-id="e0958-117">**X AVOID** 참조 일치 하는 것 보다 크게 느려지지 구현 되는 경우에 참조 형식에 같음 연산자를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0958-117">**X AVOID** overloading equality operators on reference types if the implementation would be significantly slower than that of reference equality.</span></span>  
  
 <span data-ttu-id="e0958-118">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="e0958-118">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e0958-119">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="e0958-119">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0958-120">참조</span><span class="sxs-lookup"><span data-stu-id="e0958-120">See also</span></span>

- [<span data-ttu-id="e0958-121">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="e0958-121">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e0958-122">사용 지침</span><span class="sxs-lookup"><span data-stu-id="e0958-122">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
