---
title: 네임스페이스
description: 'F # 네임 스페이스를 사용 하 여 프로그램 요소 그룹에 이름을 첨부 하 여 코드를 관련 기능 영역으로 구성 하는 방법을 알아봅니다.'
ms.date: 12/08/2018
ms.openlocfilehash: bf71843349434a1ea91c58dbc0477373dbb0c449
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796134"
---
# <a name="namespaces"></a><span data-ttu-id="0bbf6-103">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="0bbf6-103">Namespaces</span></span>

<span data-ttu-id="0bbf6-104">네임 스페이스를 사용 하면 F # 프로그램 요소 그룹에 이름을 첨부 하 여 코드를 관련 기능 영역으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="0bbf6-105">네임 스페이스는 일반적으로 F # 파일의 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="0bbf6-106">구문</span><span class="sxs-lookup"><span data-stu-id="0bbf6-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="0bbf6-107">설명</span><span class="sxs-lookup"><span data-stu-id="0bbf6-107">Remarks</span></span>

<span data-ttu-id="0bbf6-108">네임 스페이스에 코드를 저장 하려면 파일의 첫 번째 선언에서 네임 스페이스를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="0bbf6-109">그러면 파일의 다른 네임 스페이스 선언이 추가로 존재 하지 않는 경우 전체 파일의 내용이 네임 스페이스의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="0bbf6-110">이 경우 다음 네임 스페이스 선언이 첫 번째 네임 스페이스 내에 있는 것으로 간주 될 때까지 모든 코드를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="0bbf6-111">네임 스페이스에는 값과 함수를 직접 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="0bbf6-112">대신, 값 및 함수는 모듈에 포함 되어야 하며, 모듈은 네임 스페이스에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="0bbf6-113">네임 스페이스는 형식 모듈을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="0bbf6-114">XML 문서 주석은 네임 스페이스 위에 선언 될 수 있지만 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="0bbf6-115">컴파일러 지시문은 네임 스페이스 위에 선언 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="0bbf6-116">네임 스페이스는 네임 스페이스 키워드를 사용 하 여 명시적으로 선언 하거나 모듈을 선언할 때 암시적으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="0bbf6-117">네임 스페이스를 명시적으로 선언 하려면 namespace 키워드와 네임 스페이스 이름을 차례로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="0bbf6-118">다음 예제에서는 형식 및 해당 네임 스페이스에 포함 된 `Widgets` 모듈을 사용 하 여 네임 스페이스를 선언 하는 코드 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="0bbf6-119">파일의 전체 내용이 한 모듈에 있는 경우 `module` 키워드를 사용 하 고 정규화 된 모듈 이름에 새 네임 스페이스 이름을 제공 하 여 네임 스페이스를 암시적으로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="0bbf6-120">다음 예제에서는 함수를 포함 하는 네임 스페이스 `Widgets` 및 모듈 `WidgetsModule`을 선언 하는 코드 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="0bbf6-121">다음 코드는 앞의 코드와 동일 하지만 모듈은 로컬 모듈 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="0bbf6-122">이 경우 네임 스페이스는 자체 줄에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="0bbf6-123">하나 이상의 네임 스페이스에서 둘 이상의 모듈이 동일한 파일에 필요한 경우에는 로컬 모듈 선언을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="0bbf6-124">로컬 모듈 선언을 사용 하는 경우 모듈 선언에서 정규화 된 네임 스페이스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="0bbf6-125">다음 코드는 네임 스페이스 선언 및 두 개의 로컬 모듈 선언이 있는 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="0bbf6-126">이 경우 모듈은 네임 스페이스에 직접 포함 됩니다. 파일과 이름이 같은 암시적으로 생성 된 모듈이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="0bbf6-127">`do` 바인딩과 같은 파일의 다른 모든 코드는 네임 스페이스에 있지만 내부 모듈에는 없지만 모듈 이름을 사용 하 여 모듈 멤버 `widgetFunction` 를 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="0bbf6-128">이 예제의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="0bbf6-129">자세한 내용은 [모듈](modules.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="0bbf6-130">중첩 된 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="0bbf6-130">Nested Namespaces</span></span>

<span data-ttu-id="0bbf6-131">중첩 된 네임 스페이스를 만드는 경우 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="0bbf6-132">그렇지 않으면 새 최상위 네임 스페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="0bbf6-133">네임 스페이스 선언에서는 들여쓰기가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="0bbf6-134">다음 예제에서는 중첩 된 네임 스페이스를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="0bbf6-135">파일 및 어셈블리의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="0bbf6-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="0bbf6-136">네임 스페이스는 단일 프로젝트 또는 컴파일에서 여러 파일에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="0bbf6-137">*네임 스페이스 조각* 이라는 용어는 한 파일에 포함 된 네임 스페이스 부분을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="0bbf6-138">네임 스페이스는 여러 어셈블리에 걸쳐 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="0bbf6-139">예를 들어, `System` 네임 스페이스는 많은 어셈블리에 걸쳐 있고 여러 개의 중첩 된 네임 스페이스를 포함 하는 전체 .NET Framework를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="0bbf6-140">전역 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="0bbf6-140">Global Namespace</span></span>

<span data-ttu-id="0bbf6-141">미리 정의 된 네임 스페이스 `global` 를 사용 하 여 .net 최상위 네임 스페이스에 이름을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="0bbf6-142">또한 전역을 사용 하 여 최상위 .NET 네임 스페이스를 참조할 수 있습니다. 예를 들어 다른 네임 스페이스와의 이름 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="0bbf6-143">재귀 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="0bbf6-143">Recursive namespaces</span></span>

<span data-ttu-id="0bbf6-144">네임 스페이스를 재귀적으로 선언 하 여 포함 된 모든 코드가 상호 재귀 되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="0bbf6-145">이 작업은를 `namespace rec`통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="0bbf6-146">를 사용 `namespace rec` 하면 형식 및 모듈 간에 상호 참조 코드를 작성할 수 없는 일부 pains을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="0bbf6-147">이에 대 한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

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

<span data-ttu-id="0bbf6-148">예외 `DontSqueezeTheBananaException` 와 클래스 `Banana` 는 둘 다 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="0bbf6-149">또한 모듈과 `BananaHelpers` 클래스가 `Banana` 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="0bbf6-150">`MutualReferences` 네임 스페이스에서 키워드를 `rec` 제거한 경우 F #을 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="0bbf6-151">이 기능은 최상위 [모듈](modules.md)에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbf6-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0bbf6-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bbf6-152">See also</span></span>

- [<span data-ttu-id="0bbf6-153">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="0bbf6-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0bbf6-154">모듈</span><span class="sxs-lookup"><span data-stu-id="0bbf6-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="0bbf6-155">F # RFC FS-1009-파일 내에서 더 큰 범위에 대해 상호 참조 형식 및 모듈 허용</span><span class="sxs-lookup"><span data-stu-id="0bbf6-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
