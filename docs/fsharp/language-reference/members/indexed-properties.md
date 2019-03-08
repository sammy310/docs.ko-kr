---
title: 인덱싱된 속성
description: 인덱싱된 속성에 대해 알아봅니다 F#를 정렬 된 데이터에 대 한 배열 유사 액세스를 허용 합니다.
ms.date: 10/17/2018
ms.openlocfilehash: bc330641c451973ddefa0a34fe6e757a808f6cb7
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678610"
---
# <a name="indexed-properties"></a><span data-ttu-id="1adb6-103">인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="1adb6-103">Indexed Properties</span></span>

<span data-ttu-id="1adb6-104">순서가 지정 된 데이터에 대 한 추상화 하는 클래스를 정의 하는 경우 기본 구현에 노출 하지 않고 해당 데이터에 대 한 인덱싱된 액세스를 제공 하는 데 도움이 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="1adb6-105">그러려면는 `Index` 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-105">This is done with the `Index` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="1adb6-106">구문</span><span class="sxs-lookup"><span data-stu-id="1adb6-106">Syntax</span></span>

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="1adb6-107">설명</span><span class="sxs-lookup"><span data-stu-id="1adb6-107">Remarks</span></span>

<span data-ttu-id="1adb6-108">이전 구문 형식의 둘 다 있는 인덱싱된 속성을 정의 하는 방법을 보여 줍니다는 `get` 및 `set` 메서드를가 `get` 메서드만 있거나는 `set` 방법 으로만 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="1adb6-109">또한만 get 및 set만 나와 있는 구문에 대 한 표시 된 구문은 모두 결합 하 고 get 및 set를 둘 다 있는 속성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="1adb6-110">이 두 번째 형식은 get에 다른 액세스 가능성 한정자 및 특성을 배치 하 고 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="1adb6-111">이름을 사용 하 여 `Item`, 컴파일러는 인덱싱된 기본 속성으로 속성을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="1adb6-112">A *인덱싱된 기본 속성* 개체 인스턴스에서 배열 유사 구문을 사용 하 여 액세스할 수 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="1adb6-113">예를 들어 경우 `o` 구문은이 속성을 정의 하는 형식의 개체인 `o.[index]` 속성에 액세스 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="1adb6-114">기본이 아닌 인덱싱된 속성에 액세스 하기 위한 구문은 속성 및 일반 멤버와 마찬가지로 괄호로 인덱스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="1adb6-115">예를 들어 경우 속성 `o` 라고 `Ordinal`, 작성 `o.Ordinal(index)` 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="1adb6-116">사용 하는 폼에 관계 없이 항상 set 메서드 인덱싱된 속성에 대 한 커리 된 폼을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="1adb6-117">커리 된 함수에 대 한 자세한 내용은 [함수](../functions/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="1adb6-118">예제</span><span class="sxs-lookup"><span data-stu-id="1adb6-118">Example</span></span>

<span data-ttu-id="1adb6-119">다음 코드 예제에서는 정 및 기본 및 get 및 set 메서드는 기본이 아닌 인덱싱된 속성의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="1adb6-120">출력</span><span class="sxs-lookup"><span data-stu-id="1adb6-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="1adb6-121">여러 인덱스 값을 사용 하 여 인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="1adb6-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="1adb6-122">인덱싱된 속성 둘 이상의 인덱스 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="1adb6-123">이 경우 값 속성을 사용 하는 경우 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="1adb6-124">이러한 속성의 set 메서드에 두 개의 커리 된 인수는 첫 번째는 키가 포함 된 튜플 및는 두 번째 값을 설정 하는 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="1adb6-125">다음 코드는 여러 인덱스 값을 사용 하 여 인덱싱된 속성의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1adb6-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="1adb6-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="1adb6-126">See also</span></span>

- [<span data-ttu-id="1adb6-127">멤버</span><span class="sxs-lookup"><span data-stu-id="1adb6-127">Members</span></span>](index.md)
