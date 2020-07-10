---
title: 튜플
description: '서로 다른 형식의 명명 되지 않았지만 정렬 된 값의 그룹인 F # 튜플에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 5d26fd5d7ec5b4939a895a6d2a6a0d7fc6c6c733
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173291"
---
# <a name="tuples"></a><span data-ttu-id="e68b8-103">튜플</span><span class="sxs-lookup"><span data-stu-id="e68b8-103">Tuples</span></span>

<span data-ttu-id="e68b8-104">*튜플은* 다른 형식의 명명 되지 않은 정렬 된 값을 그룹화 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="e68b8-105">튜플은 참조 형식 또는 구조체 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="e68b8-106">구문</span><span class="sxs-lookup"><span data-stu-id="e68b8-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="e68b8-107">설명</span><span class="sxs-lookup"><span data-stu-id="e68b8-107">Remarks</span></span>

<span data-ttu-id="e68b8-108">위의 구문에서 각 *요소* 는 유효한 F # 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="e68b8-109">예</span><span class="sxs-lookup"><span data-stu-id="e68b8-109">Examples</span></span>

<span data-ttu-id="e68b8-110">튜플의 예로는 같거나 다른 형식의 쌍, 삼중 쌍 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="e68b8-111">다음 코드에서는 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="e68b8-112">개별 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="e68b8-112">Obtaining Individual Values</span></span>

<span data-ttu-id="e68b8-113">다음 코드와 같이 패턴 일치를 사용 하 여 튜플 요소의 이름에 액세스 하 고 해당 이름을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="e68b8-114">바인딩을 통해 식 외부의 패턴 일치를 통해 튜플을 분해할 수도 있습니다 `match` `let` .</span><span class="sxs-lookup"><span data-stu-id="e68b8-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="e68b8-115">또는 튜플에서 함수에 대 한 입력으로 일치를 패턴으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="e68b8-116">튜플의 요소가 하나만 필요한 경우에는 필요 하지 않은 값에 대 한 새 이름을 만드는 것을 방지 하기 위해 와일드 카드 문자 (밑줄)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="e68b8-117">참조 튜플에 있는 요소를 구조체 튜플로 복사 하는 것도 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="e68b8-118">함수와 `fst` `snd` (참조 튜플을 해당)는 각각 튜플의 첫 번째 및 두 번째 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="e68b8-119">삼중의 세 번째 요소를 반환 하는 기본 제공 함수는 없지만 다음과 같이 간단 하 게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="e68b8-120">일반적으로 패턴 일치를 사용 하 여 개별 튜플 요소에 액세스 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="e68b8-121">튜플 사용</span><span class="sxs-lookup"><span data-stu-id="e68b8-121">Using Tuples</span></span>

<span data-ttu-id="e68b8-122">튜플은 다음 예제와 같이 함수에서 여러 값을 반환 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="e68b8-123">이 예에서는 정수 나누기를 수행 하 고 작업의 반올림 된 결과를 튜플 쌍의 첫 번째 멤버로 반환 하 고 나머지는 쌍의 두 번째 멤버로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="e68b8-124">일반적인 함수 구문에서 암시 하는 함수 인수의 암시적 currying을 방지 하려는 경우 튜플을 함수 인수로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="e68b8-125">함수를 정의 하기 위한 일반적인 구문을 `let sum a b = a + b` 사용 하면 다음 코드와 같이 함수의 첫 번째 인수에 대 한 부분 응용 프로그램용 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="e68b8-126">튜플을 매개 변수로 사용 하면 currying가 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="e68b8-127">자세한 내용은 [함수](./functions/index.md)에서 "인수 부분 적용"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e68b8-127">For more information, see "Partial Application of Arguments" in [Functions](./functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="e68b8-128">튜플 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="e68b8-128">Names of Tuple Types</span></span>

<span data-ttu-id="e68b8-129">튜플 형식의 이름을 작성 하는 경우 기호를 사용 하 여 `*` 요소를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="e68b8-130">, 및와 같이로 구성 된 튜플의 경우 `int` `float` `string` `(10, 10.0, "ten")` 형식은 다음과 같이 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="e68b8-131">C # 튜플 상호 운용</span><span class="sxs-lookup"><span data-stu-id="e68b8-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="e68b8-132">C # 7.0에는 언어에 대 한 튜플이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="e68b8-133">C #의 튜플은 구조체 이며 F #의 구조체 튜플에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="e68b8-134">C #과 상호 운용 해야 하는 경우 구조체 튜플을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="e68b8-135">이렇게 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-135">This is easy to do.</span></span>  <span data-ttu-id="e68b8-136">예를 들어 튜플을 c # 클래스에 전달 하 고 그 결과를 사용 해야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

<span data-ttu-id="e68b8-137">F # 코드에서 구조체 튜플을 매개 변수로 전달 하 고 결과를 구조체 튜플로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="e68b8-138">참조 튜플 및 구조체 튜플 간 변환</span><span class="sxs-lookup"><span data-stu-id="e68b8-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="e68b8-139">참조 튜플 및 구조체 튜플의 기본 표현은 완전히 다르므로 암시적으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="e68b8-140">즉, 다음과 같은 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="e68b8-141">하나의 튜플에 패턴 일치를 사용 하 고 구성 요소를 사용 하 여 다른 튜플을 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="e68b8-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-142">For example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="e68b8-143">참조 튜플의 컴파일된 형태</span><span class="sxs-lookup"><span data-stu-id="e68b8-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="e68b8-144">이 섹션에서는 컴파일될 때 튜플의 형태에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="e68b8-145">.NET Framework 3.5를 대상으로 하지 않는 한이 정보는 읽을 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="e68b8-146">튜플은 인자 수에서 오버 로드 된 여러 제네릭 형식 중 하나의 개체 `System.Tuple` 또는 형식 매개 변수의 수로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="e68b8-147">튜플 형식은 c # 또는 Visual Basic와 같은 다른 언어에서 볼 때 또는 F # 구문을 인식 하지 않는 도구를 사용 하는 경우이 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="e68b8-148">`Tuple`형식은 .NET Framework 4에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="e68b8-149">.NET Framework의 이전 버전을 대상으로 하는 경우 컴파일러는 F # 핵심 라이브러리의 2.0 버전에서 사용 하는 system.string [버전을 사용](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="e68b8-150">이 라이브러리의 형식은 .NET Framework의 2.0, 3.0 및 3.5 버전을 대상으로 하는 응용 프로그램에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="e68b8-151">형식 전달은 .NET Framework 2.0와 .NET Framework 4 F # 구성 요소 간의 이진 호환성을 보장 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="e68b8-152">구조체 튜플의 컴파일된 형태</span><span class="sxs-lookup"><span data-stu-id="e68b8-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="e68b8-153">구조체 튜플 (예: `struct (x, y)` )은 기본적으로 참조 튜플과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="e68b8-154">이러한 <xref:System.ValueTuple> 매개 변수는 인자 수로 오버 로드 된 형식 또는 형식 매개 변수 수로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="e68b8-155">이러한 값은 [c # 7.0 튜플](../../csharp/language-reference/builtin-types/value-tuples.md) 및 [Visual Basic 2017 튜플](../../visual-basic/programming-guide/language-features/data-types/tuples.md)및 상호 운용 양방향으로와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68b8-155">They are equivalent to [C# 7.0 Tuples](../../csharp/language-reference/builtin-types/value-tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="e68b8-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e68b8-156">See also</span></span>

- [<span data-ttu-id="e68b8-157">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="e68b8-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="e68b8-158">F# 형식</span><span class="sxs-lookup"><span data-stu-id="e68b8-158">F# Types</span></span>](fsharp-types.md)
