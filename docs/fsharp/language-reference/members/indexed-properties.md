---
title: 인덱싱된 속성
description: 정렬 된 데이터에 대 F#한 배열 유사 액세스를 허용 하는의 인덱싱된 속성에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976606"
---
# <a name="indexed-properties"></a><span data-ttu-id="2c512-103">인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="2c512-103">Indexed Properties</span></span>

<span data-ttu-id="2c512-104">순서가 지정 된 데이터를 추상화 하는 클래스를 정의 하는 경우 기본 구현을 노출 하지 않고 해당 데이터에 대 한 인덱싱된 액세스를 제공 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="2c512-105">`Item` 멤버를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c512-106">구문</span><span class="sxs-lookup"><span data-stu-id="2c512-106">Syntax</span></span>

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="2c512-107">주의</span><span class="sxs-lookup"><span data-stu-id="2c512-107">Remarks</span></span>

<span data-ttu-id="2c512-108">이전 구문의 형식은 `get` 및 `set` 메서드를 모두 포함 하거나 `get` 메서드만 포함 하거나 `set` 메서드만 포함 하는 인덱싱된 속성을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="2c512-109">Get only에 표시 된 구문과 set only에 대 한 구문을 함께 사용할 수도 있으며 get 및 set이 모두 있는 속성을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="2c512-110">이 두 번째 형식을 사용 하면 get 및 set 메서드에 다른 액세스 가능성 한정자 및 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="2c512-111">컴파일러는 이름 `Item`를 사용 하 여 속성을 인덱싱된 기본 속성으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="2c512-112">*인덱싱된 기본 속성* 은 개체 인스턴스에서 배열 형식 구문을 사용 하 여 액세스할 수 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="2c512-113">예를 들어 `o`이이 속성을 정의 하는 형식의 개체 이면 `o.[index]` 구문을 사용 하 여 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="2c512-114">기본이 아닌 인덱싱된 속성에 액세스 하기 위한 구문은 일반 멤버와 마찬가지로 속성의 이름과 인덱스를 괄호로 묶어 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="2c512-115">예를 들어 `o`의 속성을 `Ordinal`호출 하는 경우 `o.Ordinal(index)`를 작성 하 여 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="2c512-116">사용 하는 폼에 관계 없이 항상 인덱싱된 속성의 set 메서드에 대해 커리 된 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="2c512-117">커리 되는 함수에 대 한 자세한 내용은 [함수](../functions/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c512-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="2c512-118">예제</span><span class="sxs-lookup"><span data-stu-id="2c512-118">Example</span></span>

<span data-ttu-id="2c512-119">다음 코드 예제에서는 get 및 set 메서드를 사용 하는 기본 및 기본이 아닌 인덱싱된 속성을 정의 하 고 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="2c512-120">Output</span><span class="sxs-lookup"><span data-stu-id="2c512-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="2c512-121">여러 인덱스 값이 있는 인덱싱된 속성</span><span class="sxs-lookup"><span data-stu-id="2c512-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="2c512-122">인덱싱된 속성에는 두 개 이상의 인덱스 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="2c512-123">이 경우 속성을 사용할 때 값은 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="2c512-124">이러한 속성의 set 메서드에는 두 개의 커리 된 인수가 있어야 하 고, 첫 번째 인수는 키를 포함 하는 튜플이 고, 두 번째 인수는 설정 하려는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="2c512-125">다음 코드에서는 여러 인덱스 값이 있는 인덱싱된 속성을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c512-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="2c512-126">참조</span><span class="sxs-lookup"><span data-stu-id="2c512-126">See also</span></span>

- [<span data-ttu-id="2c512-127">멤버</span><span class="sxs-lookup"><span data-stu-id="2c512-127">Members</span></span>](index.md)
