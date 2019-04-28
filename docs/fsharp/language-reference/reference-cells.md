---
title: 참조 셀
description: 설명 하는 방법 F# 참조 셀은 참조 의미론을 통해 변경할 수 있는 값을 만드는 데 사용할 수 있는 저장소 위치입니다.
ms.date: 05/16/2016
ms.openlocfilehash: e4fcd3cf1abcf5f5e3b4d5439c9215b79ff8dbcd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795405"
---
# <a name="reference-cells"></a><span data-ttu-id="1d3ff-103">참조 셀</span><span class="sxs-lookup"><span data-stu-id="1d3ff-103">Reference Cells</span></span>

<span data-ttu-id="1d3ff-104">*참조 셀* 참조 의미론을 통해 변경할 수 있는 값을 만드는 데 사용할 수 있는 저장소 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="1d3ff-105">구문</span><span class="sxs-lookup"><span data-stu-id="1d3ff-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="1d3ff-106">설명</span><span class="sxs-lookup"><span data-stu-id="1d3ff-106">Remarks</span></span>

<span data-ttu-id="1d3ff-107">값 앞에 `ref` 연산자를 사용하여 값을 캡슐화하는 새 참조 셀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="1d3ff-108">이는 변경 가능한 변수이므로 참조 셀을 만든 다음 내부 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="1d3ff-109">참조 셀은 단순한 주소가 아니라 실제 값을 저장하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="1d3ff-110">`ref` 연산자를 사용하여 참조 셀을 만들면 캡슐화되고 변경 가능한 값으로 내부 값의 복사본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="1d3ff-111">`!`(느낌표) 연산자를 사용하여 참조 셀을 역참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="1d3ff-112">다음 코드 예제에서는 참조 셀을 선언하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="1d3ff-113">출력은 `50`입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-113">The output is `50`.</span></span>

<span data-ttu-id="1d3ff-114">참조 셀은 다음과 같이 선언되는 `Ref` 제네릭 레코드 형식의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="1d3ff-115">형식 `'a ref`는 `Ref<'a>`와 같은 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="1d3ff-116">IDE의 컴파일러와 IntelliSense에서는 이 형식을 전자와 같이 표시하지만 그 내부 정의는 후자와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="1d3ff-117">`ref` 연산자는 새 참조 셀을 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="1d3ff-118">다음 코드는 `ref` 연산자의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="1d3ff-119">다음 표에는 참조 셀에 사용할 수 있는 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="1d3ff-120">연산자, 멤버 또는 필드</span><span class="sxs-lookup"><span data-stu-id="1d3ff-120">Operator, member, or field</span></span>|<span data-ttu-id="1d3ff-121">설명</span><span class="sxs-lookup"><span data-stu-id="1d3ff-121">Description</span></span>|<span data-ttu-id="1d3ff-122">형식</span><span class="sxs-lookup"><span data-stu-id="1d3ff-122">Type</span></span>|<span data-ttu-id="1d3ff-123">정의</span><span class="sxs-lookup"><span data-stu-id="1d3ff-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="1d3ff-124">`!`(역참조 연산자)</span><span class="sxs-lookup"><span data-stu-id="1d3ff-124">`!` (dereference operator)</span></span>|<span data-ttu-id="1d3ff-125">내부 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="1d3ff-126">`:=`(할당 연산자)</span><span class="sxs-lookup"><span data-stu-id="1d3ff-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="1d3ff-127">내부 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="1d3ff-128">`ref` (연산자)</span><span class="sxs-lookup"><span data-stu-id="1d3ff-128">`ref` (operator)</span></span>|<span data-ttu-id="1d3ff-129">값을 새 참조 셀로 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="1d3ff-130">`Value` (속성)</span><span class="sxs-lookup"><span data-stu-id="1d3ff-130">`Value` (property)</span></span>|<span data-ttu-id="1d3ff-131">내부 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="1d3ff-132">`contents`(레코드 필드)</span><span class="sxs-lookup"><span data-stu-id="1d3ff-132">`contents` (record field)</span></span>|<span data-ttu-id="1d3ff-133">내부 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|

<span data-ttu-id="1d3ff-134">내부 값에 액세스하는 데는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="1d3ff-135">역참조 연산자(`!`)를 통해 반환되는 값은 할당 가능한 값이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="1d3ff-136">따라서 내부 값을 수정하는 경우에는 할당 연산자(`:=`)를 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="1d3ff-137">`Value` 속성과 `contents` 필드는 둘 다 할당 가능한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="1d3ff-138">따라서 다음 코드에서와 같이 이들 속성과 필드를 사용하여 내부 값에 액세스하거나 내부 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="1d3ff-139">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="1d3ff-140">필드 `contents`는 다른 ML 버전과의 호환성을 위해 제공되며 컴파일 과정에서 이 필드로 인해 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="1d3ff-141">경고가 발생하지 않도록 하려면 `--mlcompatibility` 컴파일러 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="1d3ff-142">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="1d3ff-143">C#프로그래머는 알아야 `ref` 에서 C# 와 동일한 작업을 아닙니다 `ref` 에서 F#합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="1d3ff-144">구문에 해당 하는 F# 됩니다 [byref](byrefs.md)는 참조 셀에서 다른 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="1d3ff-145">값으로 표시 `mutable`에 자동으로 승격 될 수 있습니다 `'a ref` 클로저;에 의해 캡처된 참조 [값](values/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3ff-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1d3ff-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="1d3ff-146">See also</span></span>

- [<span data-ttu-id="1d3ff-147">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="1d3ff-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="1d3ff-148">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1d3ff-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="1d3ff-149">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="1d3ff-149">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="1d3ff-150">값</span><span class="sxs-lookup"><span data-stu-id="1d3ff-150">Values</span></span>](values/index.md)
