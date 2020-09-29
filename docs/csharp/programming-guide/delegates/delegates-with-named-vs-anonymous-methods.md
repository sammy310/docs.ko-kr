---
title: '대리자 비교: 명명된 메서드 및 무명 메서드 - C# 프로그래밍 가이드'
description: 명명된 메서드를 사용하는 대리자와 무명 메서드를 사용하는 대리자를 비교합니다. 코드 예제를 살펴보고 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], with named vs. anonymous methods
- methods [C#], in delegates
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
ms.openlocfilehash: d8d2c6d8c7792b81f2fc2e25d0836e3780e58e52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202502"
---
# <a name="delegates-with-named-vs-anonymous-methods-c-programming-guide"></a><span data-ttu-id="375e5-104">대리자 비교: 명명된 메서드 및 무명 메서드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="375e5-104">Delegates with Named vs. Anonymous Methods (C# Programming Guide)</span></span>

<span data-ttu-id="375e5-105">[대리자](../../language-reference/builtin-types/reference-types.md)는 명명된 메서드에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can be associated with a named method.</span></span> <span data-ttu-id="375e5-106">명명된 메서드를 사용하여 대리자를 인스턴스화하면 메서드가 매개 변수로 전달됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-106">When you instantiate a delegate by using a named method, the method is passed as a parameter, for example:</span></span>  
  
 [!code-csharp[csProgGuideDelegates#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#1)]  
  
 <span data-ttu-id="375e5-107">이 코드는 명명된 메서드를 사용하여 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-107">This is called using a named method.</span></span> <span data-ttu-id="375e5-108">명명된 메서드를 사용하여 생성된 대리자는 [정적](../../language-reference/keywords/static.md) 메서드 또는 인스턴스 메서드를 캡슐화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-108">Delegates constructed with a named method can encapsulate either a [static](../../language-reference/keywords/static.md) method or an instance method.</span></span> <span data-ttu-id="375e5-109">명명된 메서드는 이전 버전의 C#에서 대리자를 인스턴스화할 수 있는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-109">Named methods are the only way to instantiate a delegate in earlier versions of C#.</span></span> <span data-ttu-id="375e5-110">그러나 새 메서드 생성이 불필요한 오버헤드인 경우 C#에서 대리자를 인스턴스화하고 호출 시 대리자에서 처리할 코드 블록을 즉시 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-110">However, in a situation where creating a new method is unwanted overhead, C# enables you to instantiate a delegate and immediately specify a code block that the delegate will process when it is called.</span></span> <span data-ttu-id="375e5-111">블록에는 람다 식 또는 무명 메서드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-111">The block can contain either a lambda expression or an anonymous method.</span></span> <span data-ttu-id="375e5-112">자세한 내용은 [무명 함수](../statements-expressions-operators/anonymous-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="375e5-112">For more information, see [Anonymous Functions](../statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="375e5-113">설명</span><span class="sxs-lookup"><span data-stu-id="375e5-113">Remarks</span></span>  

 <span data-ttu-id="375e5-114">대리자 매개 변수로 전달하는 메서드에는 대리자 선언과 동일한 시그니처가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-114">The method that you pass as a delegate parameter must have the same signature as the delegate declaration.</span></span>  
  
 <span data-ttu-id="375e5-115">대리자 인스턴스는 정적 또는 인스턴스 메서드를 캡슐화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-115">A delegate instance may encapsulate either static or instance method.</span></span>  
  
 <span data-ttu-id="375e5-116">대리자는 [out](../../language-reference/keywords/out-parameter-modifier.md) 매개 변수를 사용할 수 있지만, 멀티캐스트 이벤트 대리자의 경우 호출될 대리자를 알 수 없기 때문에 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-116">Although the delegate can use an [out](../../language-reference/keywords/out-parameter-modifier.md) parameter, we do not recommend its use with multicast event delegates because you cannot know which delegate will be called.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="375e5-117">예제 1</span><span class="sxs-lookup"><span data-stu-id="375e5-117">Example 1</span></span>  

 <span data-ttu-id="375e5-118">다음은 대리자를 선언하고 사용하는 간단한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-118">The following is a simple example of declaring and using a delegate.</span></span> <span data-ttu-id="375e5-119">대리자 `Del` 및 연결된 메서드 `MultiplyNumbers`에 동일한 시그니처가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-119">Notice that both the delegate, `Del`, and the associated method, `MultiplyNumbers`, have the same signature</span></span>  
  
 [!code-csharp[csProgGuideDelegates#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#2)]  
  
## <a name="example-2"></a><span data-ttu-id="375e5-120">예제 2</span><span class="sxs-lookup"><span data-stu-id="375e5-120">Example 2</span></span>  

 <span data-ttu-id="375e5-121">다음 예제에서는 한 대리자가 정적 메서드와 인스턴스 메서드 모두에 매핑되며 각각의 특정 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="375e5-121">In the following example, one delegate is mapped to both static and instance methods and returns specific information from each.</span></span>  
  
 [!code-csharp[csProgGuideDelegates#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="375e5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="375e5-122">See also</span></span>

- [<span data-ttu-id="375e5-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="375e5-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="375e5-124">대리자</span><span class="sxs-lookup"><span data-stu-id="375e5-124">Delegates</span></span>](./index.md)
- [<span data-ttu-id="375e5-125">대리자를 결합하는 방법(멀티캐스트 대리자)</span><span class="sxs-lookup"><span data-stu-id="375e5-125">How to combine delegates (Multicast Delegates)</span></span>](./how-to-combine-delegates-multicast-delegates.md)
- [<span data-ttu-id="375e5-126">이벤트</span><span class="sxs-lookup"><span data-stu-id="375e5-126">Events</span></span>](../events/index.md)
