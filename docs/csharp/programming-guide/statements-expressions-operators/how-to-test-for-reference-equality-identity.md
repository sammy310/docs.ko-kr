---
title: 참조 같음(ID)을 테스트하는 방법 - C# 프로그래밍 가이드
description: 참조 같음(ID)을 테스트하는 방법을 알아봅니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 148f37b37639061e84cefafc5f057e6e7b54563f
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899154"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="8224f-104">참조 같음(ID)을 테스트하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8224f-104">How to test for reference equality (Identity) (C# Programming Guide)</span></span>

<span data-ttu-id="8224f-105">형식에서 참조 같음 비교를 지원하기 위해 사용자 지정 논리를 구현할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-105">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="8224f-106">이 기능은 정적 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 메서드가 모든 형식에 대해 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-106">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="8224f-107">다음 예제에서는 두 변수에 *참조 같음* 이 있는지 여부, 즉 메모리의 동일한 개체를 참조하는지 여부를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-107">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="8224f-108">또한 이 예제에서는 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>가 값 형식에 대해 항상 `false`를 반환하는 이유 및 문자열 일치를 확인하는 데 <xref:System.Object.ReferenceEquals%2A>를 사용하면 안 되는 이유를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-108">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8224f-109">예제</span><span class="sxs-lookup"><span data-stu-id="8224f-109">Example</span></span>  

 [!code-csharp[TestingReferenceEquality](snippets/how-to-test-for-reference-equality-identity/Program.cs)]  
  
 <span data-ttu-id="8224f-110"><xref:System.Object?displayProperty=nameWithType> 유니버설 기본 클래스의 `Equals` 구현에서도 참조 같음 검사를 수행하지만 클래스가 메서드를 재정의할 경우 결과가 예상과 다를 수 있기 때문에 이 기능은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-110">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="8224f-111">`==` 및 `!=` 연산자의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-111">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="8224f-112">참조 형식에서 작동하는 경우 `==` 및 `!=`의 기본 동작은 참조 같음 검사를 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-112">When they are operating on reference types, the default behavior of `==` and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="8224f-113">그러나 파생 클래스에서 연산자를 오버로드하여 값 같음 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-113">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="8224f-114">잠재적인 오류를 최소화하려면 두 개체에 참조 같음이 있는지 여부를 확인해야 할 때 항상 <xref:System.Object.ReferenceEquals%2A>를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-114">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="8224f-115">동일한 어셈블리 내의 상수 문자열은 항상 런타임에서 인턴 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-115">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="8224f-116">즉, 고유한 각 리터럴 문자열의 인스턴스 하나만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-116">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="8224f-117">그러나 런타임은 런타임에 생성된 문자열이 인턴 지정되도록 보장하지 않으며, 서로 다른 어셈블리에 있는 동일한 두 상수 문자열이 인턴 지정되도록 보장하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8224f-117">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8224f-118">참조</span><span class="sxs-lookup"><span data-stu-id="8224f-118">See also</span></span>

- [<span data-ttu-id="8224f-119">같음 비교</span><span class="sxs-lookup"><span data-stu-id="8224f-119">Equality Comparisons</span></span>](./equality-comparisons.md)
