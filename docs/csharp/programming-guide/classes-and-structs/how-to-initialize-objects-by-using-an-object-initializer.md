---
title: 개체 이니셜라이저를 사용하여 개체를 초기화하는 방법 - C# 프로그래밍 가이드
description: 개체 이니셜라이저를 사용하여 생성자를 호출하지 않고 C#에서 형식 개체를 초기화하는 방법에 대해 알아봅니다. 개체 이니셜라이저를 사용하여 익명 형식을 정의합니다.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0c2d38713a1fdefd922234a02e23518c0f00add5
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512784"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="b8b9e-104">개체 이니셜라이저를 사용하여 개체를 초기화하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="b8b9e-104">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="b8b9e-105">개체 이니셜라이저를 사용하여 형식에 대한 생성자를 명시적으로 호출하지 않고 선언적 방식으로 형식 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-105">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="b8b9e-106">다음 예제에서는 명명된 개체와 함께 개체 이니셜라이저를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-106">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="b8b9e-107">컴파일러는 먼저 매개 변수 없는 인스턴스 생성자에 액세스한 다음 멤버 초기화를 처리하여 개체 이니셜라이저를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-107">The compiler processes object initializers by first accessing the parameterless instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="b8b9e-108">따라서 클래스에서 매개 변수가 없는 생성자가 `private`으로 선언된 경우 공용 액세스가 필요한 개체 이니셜라이저는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-108">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="b8b9e-109">무명 형식을 정의하는 경우 개체 이니셜라이저를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-109">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="b8b9e-110">자세한 내용은 [쿼리에서 요소 속성의 하위 집합을 반환하는 방법](how-to-return-subsets-of-element-properties-in-a-query.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-110">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8b9e-111">예제</span><span class="sxs-lookup"><span data-stu-id="b8b9e-111">Example</span></span>  

<span data-ttu-id="b8b9e-112">다음 예제에서는 개체 이니셜라이저를 사용하여 새 `StudentName` 형식을 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-112">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="b8b9e-113">이 예제에서는 `StudentName` 형식의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-113">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="b8b9e-114">개체 이니셜라이저를 사용하여 개체의 이니셜라이저를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-114">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="b8b9e-115">다음 예제에서는 인덱서를 사용하여 여러 포지션의 선수를 가져오고 설정하는 `BaseballTeam` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-115">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="b8b9e-116">이 이니셜라이저는 포지션을 가리키는 약어 또는 각 포지션에 사용되는 번호를 기준으로 선수에게 야구 득점표를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b9e-116">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="b8b9e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8b9e-117">See also</span></span>

- [<span data-ttu-id="b8b9e-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b8b9e-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b8b9e-119">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="b8b9e-119">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
