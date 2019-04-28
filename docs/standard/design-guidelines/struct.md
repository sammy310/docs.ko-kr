---
title: 구조체 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: KrzysztofCwalina
ms.openlocfilehash: cc5b8d7effda31b0236477b217bccf5cf2137f8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650143"
---
# <a name="struct-design"></a><span data-ttu-id="ce2fa-102">구조체 디자인</span><span class="sxs-lookup"><span data-stu-id="ce2fa-102">Struct Design</span></span>
<span data-ttu-id="ce2fa-103">범용 값 형식 대부분의 구조체를 해당 C# 키워드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-103">The general-purpose value type is most often referred to as a struct, its C# keyword.</span></span> <span data-ttu-id="ce2fa-104">이 섹션에서는 일반 구조체 디자인에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-104">This section provides guidelines for general struct design.</span></span>  
  
 <span data-ttu-id="ce2fa-105">**X DO NOT** 구조체에 대 한 기본 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-105">**X DO NOT** provide a default constructor for a struct.</span></span>  
  
 <span data-ttu-id="ce2fa-106">이 지침은 다음 배열을 구조체를 배열의 각 항목에 대해 생성자를 실행할 필요 없이 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-106">Following this guideline allows arrays of structs to be created without having to run the constructor on each item of the array.</span></span> <span data-ttu-id="ce2fa-107">C#을 허용 하지 않도록 구조체에는 기본 생성자를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-107">Notice that C# does not allow structs to have default constructors.</span></span>  
  
 <span data-ttu-id="ce2fa-108">**X DO NOT** 변경할 수 있는 값 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-108">**X DO NOT** define mutable value types.</span></span>  
  
 <span data-ttu-id="ce2fa-109">변경할 수 있는 값 형식에는 몇 가지 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-109">Mutable value types have several problems.</span></span> <span data-ttu-id="ce2fa-110">예를 들어, 속성 getter에서 값 형식을 반환 하는 경우 호출자에 게 복사본을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-110">For example, when a property getter returns a value type, the caller receives a copy.</span></span> <span data-ttu-id="ce2fa-111">복사본을 암시적으로 만들어지기 때문에 개발자가 알지 못할 복사 하 고 원래 값이 아니라 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-111">Because the copy is created implicitly, developers might not be aware that they are mutating the copy, and not the original value.</span></span> <span data-ttu-id="ce2fa-112">또한 일부 언어 (특히에서 동적 언어) 문제가 있으므로 변경할 수 있는 값 형식을 사용 하 여 역참조 시 로컬 변수에도, 하면 복사 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-112">Also, some languages (dynamic languages, in particular) have problems using mutable value types because even local variables, when dereferenced, cause a copy to be made.</span></span>  
  
 <span data-ttu-id="ce2fa-113">**✓ DO** 0으로 설정 되어 있는 모든 인스턴스 데이터는 상태, false 또는 적절 하 게 null 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-113">**✓ DO** ensure that a state where all instance data is set to zero, false, or null (as appropriate) is valid.</span></span>  
  
 <span data-ttu-id="ce2fa-114">이 구조체 배열을 만들어질 때 잘못 된 인스턴스도 실수로 생성을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-114">This prevents accidental creation of invalid instances when an array of the structs is created.</span></span>  
  
 <span data-ttu-id="ce2fa-115">**✓ DO** 구현 <xref:System.IEquatable%601> 값 형식에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-115">**✓ DO** implement <xref:System.IEquatable%601> on value types.</span></span>  
  
 <span data-ttu-id="ce2fa-116"><xref:System.Object.Equals%2A?displayProperty=nameWithType> 하면 boxing, 값 형식에 메서드 및 리플렉션을 사용 하 여 해당 기본 구현은 매우 효율적 이므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-116">The <xref:System.Object.Equals%2A?displayProperty=nameWithType> method on value types causes boxing, and its default implementation is not very efficient, because it uses reflection.</span></span> <span data-ttu-id="ce2fa-117"><xref:System.IEquatable%601.Equals%2A> 훨씬 더 나은 성능이 있습니다 및 boxing 되지 것입니다 있도록 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-117"><xref:System.IEquatable%601.Equals%2A> can have much better performance and can be implemented so that it will not cause boxing.</span></span>  
  
 <span data-ttu-id="ce2fa-118">**X DO NOT** 명시적으로 확장 <xref:System.ValueType>합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-118">**X DO NOT** explicitly extend <xref:System.ValueType>.</span></span> <span data-ttu-id="ce2fa-119">사실 대부분의 언어가를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-119">In fact, most languages prevent this.</span></span>  
  
 <span data-ttu-id="ce2fa-120">일반적으로 구조체 매우 유용할 수 있지만 자주 boxed 하지는 small, single, 변경할 수 없는 값만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce2fa-120">In general, structs can be very useful but should only be used for small, single, immutable values that will not be boxed frequently.</span></span>  
  
 <span data-ttu-id="ce2fa-121">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="ce2fa-121">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ce2fa-122">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="ce2fa-122">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2fa-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="ce2fa-123">See also</span></span>

- [<span data-ttu-id="ce2fa-124">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ce2fa-124">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)
- [<span data-ttu-id="ce2fa-125">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ce2fa-125">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="ce2fa-126">클래스와 구조체 간의 선택</span><span class="sxs-lookup"><span data-stu-id="ce2fa-126">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
