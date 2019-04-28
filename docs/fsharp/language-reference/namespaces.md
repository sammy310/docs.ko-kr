---
title: 네임스페이스
description: 에 대해 알아봅니다 어떻게는 F# 네임 스페이스를 사용 하면 프로그램 요소의 그룹에 이름을 연결 하 여 관련 기능 영역으로 코드를 구성할 수 있습니다.
ms.date: 12/08/2018
ms.openlocfilehash: 526d7a07e4804751811c15fa91b0c74c1954d591
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666393"
---
# <a name="namespaces"></a><span data-ttu-id="9e1e2-103">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9e1e2-103">Namespaces</span></span>

<span data-ttu-id="9e1e2-104">네임 스페이스 이름을 그룹에 연결할 수 있도록 하 여 관련 기능 영역으로 코드를 구성할 수 있습니다 F# 요소를 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="9e1e2-105">네임 스페이스에서 일반적으로 최상위 요소는 F# 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e1e2-106">구문</span><span class="sxs-lookup"><span data-stu-id="9e1e2-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="9e1e2-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e1e2-107">Remarks</span></span>

<span data-ttu-id="9e1e2-108">네임 스페이스에 코드를 배치 하려는 경우 파일의 첫 번째 선언은 네임 스페이스를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="9e1e2-109">그런 다음 전체 파일의 내용을 네임 스페이스의 일부가, 다른 네임 스페이스 선언이 없는 존재 제공 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="9e1e2-110">하는 경우 다음 네임 스페이스 선언까지 모든 코드는 첫 번째 네임 스페이스에 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="9e1e2-111">네임 스페이스 값 및 함수에 직접 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="9e1e2-112">대신 값 및 함수 모듈에 포함 되어야 하며 모듈이 네임 스페이스에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="9e1e2-113">네임 스페이스에는 모듈 형식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="9e1e2-114">XML 문서 주석 위에 네임 스페이스를 선언할 수 있습니다 있지만 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="9e1e2-115">컴파일러 지시문은 네임 스페이스 위에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="9e1e2-116">네임 스페이스 선언할 수 있습니다 명시적으로 네임 스페이스 키워드를 사용 하거나 암시적으로 모듈을 선언 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="9e1e2-117">네임 스페이스를 명시적으로 선언 하려면 네임 스페이스 이름 뒤에 네임 스페이스 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="9e1e2-118">다음 예제에서는 네임 스페이스를 선언 하는 코드 파일 `Widgets` 형식과 해당 네임 스페이스에 포함 된 모듈을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="9e1e2-119">파일의 전체 내용을 하나의 모듈에 있는 경우 선언할 수도 있습니다 네임 스페이스 암시적으로 사용 하 여는 `module` 키워드 및 정규화 된 모듈 이름에 새 네임 스페이스 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="9e1e2-120">다음 예제에서는 네임 스페이스를 선언 하는 코드 파일을 보여 줍니다 `Widgets` 및 모듈 `WidgetsModule`, 함수를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="9e1e2-121">다음 코드는 이전 코드와 동일 하지만 모듈은 로컬 모듈 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="9e1e2-122">이 경우 네임 스페이스 자체 줄에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="9e1e2-123">둘 이상의 모듈에 하나 이상의 네임 스페이스에 있는 동일한 파일에서 필요한 경우 로컬 모듈 선언 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="9e1e2-124">로컬 모듈 선언에 사용 하는 경우에 모듈 선언에 정규화 된 네임 스페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="9e1e2-125">다음 코드는 네임 스페이스 선언 및 두 개의 로컬 모듈 선언 된 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="9e1e2-126">모듈의 네임 스페이스에 직접 포함 된이 예제의 경우 파일 이름이 동일한 암시적으로 만든된 모듈이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="9e1e2-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="9e1e2-127">와 같은 파일에서 코드 다른를 `do` 되므로 모듈 멤버를 한정할 필요가 내부 모듈을 제외한 네임 스페이스에는 바인딩 `widgetFunction` 모듈 이름을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="9e1e2-128">이 예제의 출력은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="9e1e2-129">자세한 내용은 [모듈](modules.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="9e1e2-130">중첩 된 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="9e1e2-130">Nested Namespaces</span></span>

<span data-ttu-id="9e1e2-131">중첩된 된 네임 스페이스를 만들 때 완전히 서 한 정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="9e1e2-132">그렇지 않으면 새 최상위 네임 스페이스를 만들 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="9e1e2-133">들여쓰기는 네임 스페이스 선언에서 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="9e1e2-134">다음 예제에서는 중첩된 된 네임 스페이스를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="9e1e2-135">파일 및 어셈블리의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="9e1e2-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="9e1e2-136">네임 스페이스는 단일 프로젝트 또는 컴파일에서 여러 파일을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="9e1e2-137">용어 *네임 스페이스 조각* 하나의 파일에 포함 된 네임 스페이스의 일부를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="9e1e2-138">네임 스페이스에는 여러 어셈블리 걸쳐 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="9e1e2-139">예를 들어를 `System` 네임 스페이스에 걸쳐 여러 어셈블리를 여러 개의 중첩 된 네임 스페이스를 포함 합니다. 전체.NET Framework를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="9e1e2-140">전역 Namespace</span><span class="sxs-lookup"><span data-stu-id="9e1e2-140">Global Namespace</span></span>

<span data-ttu-id="9e1e2-141">미리 정의 된 네임 스페이스를 사용 하면 `global` .NET 최상위 네임 스페이스의 이름을 삽입할 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="9e1e2-142">사용할 수도 있습니다 전역 예를 들어 최상위.NET 네임 스페이스 참조를 다른 네임 스페이스와 이름 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="9e1e2-143">재귀 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="9e1e2-143">Recursive namespaces</span></span>

<span data-ttu-id="9e1e2-144">상호 재귀를 모두 포함 된 코드에 대 한 허용 하도록 자동으로 네임 스페이스를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="9e1e2-145">이 통해 이루어집니다 `namespace rec`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="9e1e2-146">사용 `namespace rec` 의 종류와 모듈 간의 상호 참조 코드를 쓸 수 없는 몇 가지 문제를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="9e1e2-147">다음은이 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="9e1e2-148">예외 `DontSqueezeTheBananaException` 및 클래스 `Banana` 모두 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="9e1e2-149">또한 모듈 `BananaHelpers` 및 클래스 `Banana` 서로 참조할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="9e1e2-150">에 표시할 수 없을 것임이 F# 를 제거한 경우 합니다 `rec` 키워드를는 `MutualReferences` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="9e1e2-151">이 기능은 또한에 사용할 수 있는 최상위 [모듈](modules.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e2-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e1e2-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e1e2-152">See also</span></span>

- [<span data-ttu-id="9e1e2-153">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="9e1e2-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="9e1e2-154">모듈</span><span class="sxs-lookup"><span data-stu-id="9e1e2-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="9e1e2-155">F#RFC FS-1009-파일 내에서 더 큰 범위를 통한 상호 참조 형식 및 모듈 허용</span><span class="sxs-lookup"><span data-stu-id="9e1e2-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)