---
title: Fixed 키워드
description: 하는 방법에 대해 알아봅니다. 'p i를 스택으로 사용 하 여 컬렉션을 방지 하기 위해 로컬 합니다 F# 'fixed' 키워드입니다.
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772660"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="f611b-103">Fixed 키워드</span><span class="sxs-lookup"><span data-stu-id="f611b-103">The fixed keyword</span></span>

<span data-ttu-id="f611b-104">F#4.1 소개를 `fixed` "고정" 스택에 로컬 수집 되거나 가비지 수집 하는 동안 이동 하지 못하게 할 수 있는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="f611b-105">하위 수준 프로그래밍 시나리오에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="f611b-106">구문</span><span class="sxs-lookup"><span data-stu-id="f611b-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="f611b-107">설명</span><span class="sxs-lookup"><span data-stu-id="f611b-107">Remarks</span></span>

<span data-ttu-id="f611b-108">이 확장에 대 한 포인터를 추출 하 고 수집 되거나 가비지 컬렉션 도중 이동 못하게 하는 이름에 바인딩할 수 있도록 식의 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="f611b-109">식에서 포인터를 통해 고정 되어는 `fixed` 키워드를 통해 식별자에 바인딩되는 `use` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="f611b-110">리소스 관리를 통해이 의미 체계가 비슷합니다는 `use` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="f611b-111">포인터는 범위에는 더 이상 고정 범위를 벗어납니다 있으면 하는 동안 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="f611b-112">`fixed` 컨텍스트 외부에서 사용할 수 없습니다는 `use` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="f611b-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="f611b-113">사용 하 여 이름으로 포인터를 바인딩해야 `use`합니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="f611b-114">사용 `fixed` 함수 또는 메서드의 식 내에서 발생 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="f611b-115">스크립트 또는 모듈 수준의 범위에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="f611b-116">모든 포인터 코드와 같은 안전 하지 않은 기능은이 및에서 사용 하는 경우 경고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f611b-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="f611b-117">예제</span><span class="sxs-lookup"><span data-stu-id="f611b-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="f611b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="f611b-118">See also</span></span>

- [<span data-ttu-id="f611b-119">NativePtr 모듈</span><span class="sxs-lookup"><span data-stu-id="f611b-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
