---
title: 튜플
description: 알아봅니다는 F# 튜플 명명 되지는 않았지만 순서가 지정 된 값의 그룹화 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: a1fc31d4dc97c0921545e53b91dcde0547002006
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755339"
---
# <a name="tuples"></a><span data-ttu-id="db590-103">튜플</span><span class="sxs-lookup"><span data-stu-id="db590-103">Tuples</span></span>

<span data-ttu-id="db590-104">A *튜플* 명명 되지는 않았지만 순서가 지정 된 값의 그룹화입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-104">A *tuple* is a grouping of unnamed but ordered values, possibly of different types.</span></span>  <span data-ttu-id="db590-105">참조 형식 또는 구조체에는 튜플 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-105">Tuples can either be reference types or structs.</span></span>

## <a name="syntax"></a><span data-ttu-id="db590-106">구문</span><span class="sxs-lookup"><span data-stu-id="db590-106">Syntax</span></span>

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a><span data-ttu-id="db590-107">설명</span><span class="sxs-lookup"><span data-stu-id="db590-107">Remarks</span></span>

<span data-ttu-id="db590-108">각 *요소* 위 구문에서 든 사용할 수 F# 식입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-108">Each *element* in the previous syntax can be any valid F# expression.</span></span>

## <a name="examples"></a><span data-ttu-id="db590-109">예제</span><span class="sxs-lookup"><span data-stu-id="db590-109">Examples</span></span>

<span data-ttu-id="db590-110">튜플의 예로 쌍, 삼중 쌍, 등과 같은 또는 다른 형식의 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-110">Examples of tuples include pairs, triples, and so on, of the same or different types.</span></span> <span data-ttu-id="db590-111">몇 가지 예는 다음 코드에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-111">Some examples are illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a><span data-ttu-id="db590-112">개별 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="db590-112">Obtaining Individual Values</span></span>

<span data-ttu-id="db590-113">사용할 수 있습니다 패턴 일치 액세스 및 튜플 요소에 대 한 이름을 할당 하려면 다음 코드 에서처럼.</span><span class="sxs-lookup"><span data-stu-id="db590-113">You can use pattern matching to access and assign names for tuple elements, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

<span data-ttu-id="db590-114">또한 외부 패턴 일치를 통해 튜플을 분해할 수는 `match` 식을 통해 `let` 바인딩:</span><span class="sxs-lookup"><span data-stu-id="db590-114">You can also deconstruct a tuple via pattern matching outside of a `match` expression via  `let` binding:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

<span data-ttu-id="db590-115">Or 패턴 수 튜플 함수에 대 한 입력으로 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-115">Or you can pattern match on tuples as inputs to functions:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

<span data-ttu-id="db590-116">튜플 요소가 하나만 필요한 경우 와일드 카드 문자 (밑줄) 필요 하지 않은 값에 대 한 새 이름을 만들지 않도록 방지 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-116">If you need only one element of the tuple, the wildcard character (the underscore) can be used to avoid creating a new name for a value that you do not need.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

<span data-ttu-id="db590-117">구조체 튜플로 참조 튜플에서 요소를 복사 하는 작업도 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-117">Copying elements from a reference tuple into a struct tuple is also simple:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

<span data-ttu-id="db590-118">함수 `fst` 고 `snd` (튜플만 참조) 첫 번째 반환 된 튜플의 요소를 각각 두 번째 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-118">The functions `fst` and `snd` (reference tuples only) return the first and second elements of a tuple, respectively.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

<span data-ttu-id="db590-119">튜플의 세 번째 요소를 반환 하는 기본 제공 함수가 있지만 쉽게 작성할 수 있습니다 하나 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-119">There is no built-in function that returns the third element of a triple, but you can easily write one as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

<span data-ttu-id="db590-120">일반적으로 개별 튜플 요소에 액세스 하려면 패턴 일치를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-120">Generally, it is better to use pattern matching to access individual tuple elements.</span></span>

## <a name="using-tuples"></a><span data-ttu-id="db590-121">튜플을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="db590-121">Using Tuples</span></span>

<span data-ttu-id="db590-122">튜플 다음 예와에서 같이 함수에서 여러 값을 반환 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-122">Tuples provide a convenient way to return multiple values from a function, as shown in the following example.</span></span> <span data-ttu-id="db590-123">이 예제에서는 정수 나누기를 수행 하 고 튜플 쌍의 첫 번째 멤버로 작업 쌍의 두 번째 구성원으로 나머지의 반올림 된 결과 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-123">This example performs integer division and returns the rounded result of the operation as a first member of a tuple pair and the remainder as a second member of the pair.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

<span data-ttu-id="db590-124">튜플 암시 일반적인 함수 구문 하는 함수 인수 암시적 커리 방지 하려는 경우 함수 인수로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-124">Tuples can also be used as function arguments when you want to avoid the implicit currying of function arguments that is implied by the usual function syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

<span data-ttu-id="db590-125">함수를 정의 하는 일반적인 구문은 `let sum a b = a + b` 다음 코드 에서처럼는 함수의 첫 번째 인수의 부분 적용 하는 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-125">The usual syntax for defining the function `let sum a b = a + b` enables you to define a function that is the partial application of the first argument of the function, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

<span data-ttu-id="db590-126">튜플을 사용 하 여 매개 변수로 (currying) 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-126">Using a tuple as the parameter disables currying.</span></span> <span data-ttu-id="db590-127">자세한 내용은 "응용 프로그램의 인수 부분"를 참조 하세요 [함수](functions/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-127">For more information, see "Partial Application of Arguments" in [Functions](functions/index.md).</span></span>

## <a name="names-of-tuple-types"></a><span data-ttu-id="db590-128">튜플 형식의 이름</span><span class="sxs-lookup"><span data-stu-id="db590-128">Names of Tuple Types</span></span>

<span data-ttu-id="db590-129">튜플 형식 이름을 작성 하는 경우 사용할는 `*` 요소를 구분 하는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-129">When you write out the name of a type that is a tuple, you use the `*` symbol to separate elements.</span></span> <span data-ttu-id="db590-130">구성 된 튜플에 대 한는 `int`, `float`, 및 `string`, 같은 `(10, 10.0, "ten")`, 종류는 다음과 같이 작성 될 수입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-130">For a tuple that consists of an `int`, a `float`, and a `string`, such as `(10, 10.0, "ten")`, the type would be written as follows.</span></span>

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a><span data-ttu-id="db590-131">C# 튜플와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="db590-131">Interoperation with C# Tuples</span></span>

<span data-ttu-id="db590-132">C# 7.0에서는 튜플 언어 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-132">C# 7.0 introduced tuples to the language.</span></span>  <span data-ttu-id="db590-133">튜플 C# 구조체 되며에서 구조체 튜플에 해당 하는 F#합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-133">Tuples in C# are structs, and are equivalent to struct tuples in F#.</span></span>  <span data-ttu-id="db590-134">C#을 사용 하 여 상호 운용 해야 하는 경우에 구조체 튜플을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-134">If you need to interoperate with C#, you must use struct tuples.</span></span>

<span data-ttu-id="db590-135">작업을 수행 하는 것과 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-135">This is easy to do.</span></span>  <span data-ttu-id="db590-136">예를 들어 C# 클래스에 튜플을 전달 하 고는 튜플을 해당 결과 사용할 수 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-136">For example, imagine you have to pass a tuple to a C# class and then consume its result, which is also a tuple:</span></span>

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

<span data-ttu-id="db590-137">에 F# 코드를 다음 구조체 튜플 매개 변수로 전달 하 고 구조체 튜플 결과 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-137">In your F# code, you can then pass a struct tuple as the parameter and consume the result as a struct tuple.</span></span>

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a><span data-ttu-id="db590-138">참조 튜플과 구조체 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="db590-138">Converting between Reference Tuples and Struct Tuples</span></span>

<span data-ttu-id="db590-139">참조 튜플과 구조체에 완전히 다른 내부 표현 되어 암시적으로 변환할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-139">Because Reference Tuples and Struct Tuples have a completely different underlying representation, they are not implicitly convertible.</span></span>  <span data-ttu-id="db590-140">즉, 다음과 같은 코드가 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-140">That is, code such as the following won't compile:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

<span data-ttu-id="db590-141">패턴 해야 1 개의 튜플이 일치 및 다른 구성 요소를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-141">You must pattern match on one tuple and construct the other with the constituent parts.</span></span>  <span data-ttu-id="db590-142">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="db590-142">For example:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a><span data-ttu-id="db590-143">컴파일된 참조 튜플 형식</span><span class="sxs-lookup"><span data-stu-id="db590-143">Compiled Form of Reference Tuples</span></span>

<span data-ttu-id="db590-144">이 섹션에서는 컴파일하면 튜플 형식의 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-144">This section explains the form of tuples when they're compiled.</span></span>  <span data-ttu-id="db590-145">정보에는.NET Framework 3.5를 대상으로 하는 경우가 아니면를 읽는 데 필요한 이하로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-145">The information here isn't necessary to read unless you are targeting .NET Framework 3.5 or lower.</span></span>

<span data-ttu-id="db590-146">튜플 형식의 몇 가지 일반, 모든 명명 된 개체 컴파일됩니다 `System.Tuple`, 인자 수, 또는 형식 매개 변수의 개수를 오버 로드 됩니다.입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-146">Tuples are compiled into objects of one of several generic types, all named `System.Tuple`, that are overloaded on the arity, or number of type parameters.</span></span> <span data-ttu-id="db590-147">볼 때 다른 언어에서 같은 튜플 형식이 형태로 나타나는 C# 또는 Visual Basic의 인식 되지 않는 도구를 사용 하는 경우 또는 F# 를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-147">Tuple types appear in this form when you view them from another language, such as C# or Visual Basic, or when you are using a tool that is not aware of F# constructs.</span></span> <span data-ttu-id="db590-148">`Tuple` 형식을.NET Framework 4에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="db590-148">The `Tuple` types were introduced in .NET Framework 4.</span></span> <span data-ttu-id="db590-149">이전 버전의.NET Framework를 대상으로 하는 경우 컴파일러의 버전을 사용 [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) 의 2.0 버전에서의 F# 핵심 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-149">If you are targeting an earlier version of the .NET Framework, the compiler uses versions of [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) from the 2.0 version of the F# Core Library.</span></span> <span data-ttu-id="db590-150">이 라이브러리의 형식은 2.0, 3.0 및 3.5 버전의.NET Framework를 대상으로 하는 응용 프로그램에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db590-150">The types in this library are used only for applications that target the 2.0, 3.0, and 3.5 versions of the .NET Framework.</span></span> <span data-ttu-id="db590-151">형식 전달을.NET Framework 2.0 및.NET Framework 4 간의 이진 호환성을 유지 하는 데 사용 됩니다 F# 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="db590-151">Type forwarding is used to ensure binary compatibility between .NET Framework 2.0 and .NET Framework 4 F# components.</span></span>

### <a name="compiled-form-of-struct-tuples"></a><span data-ttu-id="db590-152">컴파일된 구조체 튜플 형식</span><span class="sxs-lookup"><span data-stu-id="db590-152">Compiled Form of Struct Tuples</span></span>

<span data-ttu-id="db590-153">구조체 튜플 (예를 들어 `struct (x, y)`), 참조 튜플에 근본적으로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="db590-153">Struct tuples (for example, `struct (x, y)`), are fundamentally different from reference tuples.</span></span>  <span data-ttu-id="db590-154">컴파일되지는 <xref:System.ValueTuple> 형식, 형식 매개 변수의 개수나 인자 수, 오버 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db590-154">They are compiled into the <xref:System.ValueTuple> type, overloaded by arity, or the number of type parameters.</span></span>  <span data-ttu-id="db590-155">동일 [C# 7.0 튜플](../../csharp/tuples.md) 및 [Visual Basic 2017 튜플](../../visual-basic/programming-guide/language-features/data-types/tuples.md), 양방향 상호 운용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db590-155">They are equivalent to [C# 7.0 Tuples](../../csharp/tuples.md) and [Visual Basic 2017 Tuples](../../visual-basic/programming-guide/language-features/data-types/tuples.md), and interoperate bidirectionally.</span></span>

## <a name="see-also"></a><span data-ttu-id="db590-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="db590-156">See also</span></span>

- [<span data-ttu-id="db590-157">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="db590-157">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="db590-158">F# 형식</span><span class="sxs-lookup"><span data-stu-id="db590-158">F# Types</span></span>](fsharp-types.md)