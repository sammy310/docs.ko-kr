---
title: 컬렉션 이니셜라이저를 사용하여 사전을 초기화하는 방법 - C# 프로그래밍 가이드
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 1e6e7fac9dd49ad1943ac9046bd9e4932c383257
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741362"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="461e3-102">컬렉션 이니셜라이저를 사용하여 사전을 초기화하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="461e3-102">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="461e3-103"><xref:System.Collections.Generic.Dictionary%602>에는 키/값 쌍의 컬렉션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-103">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="461e3-104">해당 <xref:System.Collections.Generic.Dictionary%602.Add%2A> 메서드는 두 개의 매개 변수를 사용하며, 하나는 키에, 다른 하나는 값에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-104">Its <xref:System.Collections.Generic.Dictionary%602.Add%2A> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="461e3-105"><xref:System.Collections.Generic.Dictionary%602> 또는 여러 매개 변수를 사용하는 `Add` 메서드를 초기화하는 한 가지 방법은 다음 예제와 같이 각 매개 변수 집합을 중괄호로 묶는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-105">One way to initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, is to enclose each set of parameters in braces as shown in the following example.</span></span> <span data-ttu-id="461e3-106">또한 다음 예에서와 같이 인덱스 이니셜라이저를 사용하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-106">Another option is to use an index initializer, also shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="461e3-107">예제</span><span class="sxs-lookup"><span data-stu-id="461e3-107">Example</span></span>

<span data-ttu-id="461e3-108">다음 코드 예제에서 <xref:System.Collections.Generic.Dictionary%602>는 `StudentName` 유형의 인스턴스를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-108">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  <span data-ttu-id="461e3-109">첫 번째 초기화에서는 `Add` 메서드와 두 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-109">The first initialization uses the `Add` method with two arguments.</span></span> <span data-ttu-id="461e3-110">컴파일러는 각 `int` 키 및 `StudentName` 값 쌍에 `Add`에 대한 호출을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-110">The compiler generates a call to `Add` for each of the pairs of `int` keys and `StudentName` values.</span></span> <span data-ttu-id="461e3-111">두 번째 초기화에서는 `Dictionary` 클래스의 공용 읽기/쓰기 인덱서 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-111">The second uses a public read / write indexer method of the `Dictionary` class:</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

<span data-ttu-id="461e3-112">첫 번째 선언에서 컬렉션의 각 요소에는 두 쌍의 중괄호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-112">Note the two pairs of braces in each element of the collection in the first declaration.</span></span> <span data-ttu-id="461e3-113">안쪽 중괄호는 `StudentName`에 대한 개체 이니셜라이저를 묶고, 바깥쪽 중괄호는 `students` <xref:System.Collections.Generic.Dictionary%602>에 추가할 키/값 쌍에 대한 이니셜라이저를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-113">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="461e3-114">마지막으로, 사전에 대한 전체 컬렉션 이니셜라이저가 중괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-114">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span> <span data-ttu-id="461e3-115">두 번째 초기화에서 할당의 왼쪽은 키이고, 오른쪽은 값이며 `StudentName`에 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="461e3-115">In the second initialization, the left side of the assignment is the key and the right side is the value, using an object initializer for `StudentName`.</span></span>

## <a name="see-also"></a><span data-ttu-id="461e3-116">참조</span><span class="sxs-lookup"><span data-stu-id="461e3-116">See also</span></span>

- [<span data-ttu-id="461e3-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="461e3-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="461e3-118">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="461e3-118">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)
