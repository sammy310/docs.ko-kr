---
title: 모듈
description: 'F # 프로그램에서 f # 모듈이 값, 형식 및 함수 값과 같은 F # 코드를 그룹화 하는 방법에 대해 알아봅니다.'
ms.date: 04/24/2017
ms.openlocfilehash: 5f99bbd8069478bf0c7db2800ae545f31926728a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794366"
---
# <a name="modules"></a><span data-ttu-id="6b9ff-103">모듈</span><span class="sxs-lookup"><span data-stu-id="6b9ff-103">Modules</span></span>

<span data-ttu-id="6b9ff-104">F # 언어의 컨텍스트에서 *모듈* 은 f # 프로그램의 값, 형식 및 함수 값과 같은 f # 코드의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="6b9ff-105">모듈로 코드를 그룹화하면 관련 코드를 함께 유지하고, 프로그램의 이름 충돌을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b9ff-106">구문</span><span class="sxs-lookup"><span data-stu-id="6b9ff-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="6b9ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="6b9ff-107">Remarks</span></span>

<span data-ttu-id="6b9ff-108">F # 모듈은 형식, 값, 함수 값 및 `do` 바인딩의 코드와 같은 f # 코드 구문의 그룹화입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="6b9ff-109">정적 멤버만 있는 CLR (공용 언어 런타임) 클래스로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="6b9ff-110">모듈 선언에는 전체 파일이 모듈에 포함 되는지 여부에 따라 최상위 모듈 선언과 로컬 모듈 선언이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="6b9ff-111">최상위 모듈 선언에는 모듈의 전체 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="6b9ff-112">최상위 모듈 선언은 파일의 첫 번째 선언 으로만 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="6b9ff-113">최상위 모듈 선언에 대 한 구문에서 정규화 된 선택적 *네임 스페이스* 는 모듈이 포함 된 중첩 된 네임 스페이스 이름의 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="6b9ff-114">정규화 된 네임 스페이스는 이전에 선언 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="6b9ff-115">최상위 모듈에서 선언을 들여쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="6b9ff-116">로컬 모듈의 모든 선언을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="6b9ff-117">로컬 모듈 선언에서 해당 모듈 선언 아래에 들여쓰기 된 선언만 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="6b9ff-118">코드 파일이 최상위 모듈 선언이 나 네임 스페이스 선언으로 시작 하지 않는 경우 로컬 모듈을 포함 하 여 파일의 전체 내용은 확장명이 없는 파일의 이름과 동일한 이름을 가진 암시적으로 생성 된 최상위 모듈의 일부가 되며, 첫 번째 문자가 대문자로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="6b9ff-119">예를 들어 다음 파일을 살펴보십시오.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="6b9ff-120">이 파일은 다음과 같은 방식으로 작성 된 것 처럼 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="6b9ff-121">파일에 모듈이 여러 개 있는 경우 각 모듈에 대해 로컬 모듈 선언을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="6b9ff-122">바깥쪽 네임 스페이스를 선언 하는 경우 이러한 모듈은 바깥쪽 네임 스페이스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="6b9ff-123">바깥쪽 네임 스페이스가 선언 되지 않은 경우 모듈은 암시적으로 생성 된 최상위 모듈의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="6b9ff-124">다음 코드 예제에서는 여러 개의 모듈이 포함 된 코드 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="6b9ff-125">컴파일러는 이라는 `Multiplemodules`최상위 모듈을 암시적으로 만들며, `MyModule1` 및 `MyModule2` 는 해당 최상위 모듈에 중첩 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="6b9ff-126">프로젝트에 여러 파일이 있거나 단일 컴파일에서 있거나 라이브러리를 빌드하는 경우에는 파일 맨 위에 네임 스페이스 선언 또는 모듈 선언을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="6b9ff-127">F # 컴파일러는 프로젝트 또는 컴파일 명령줄에 파일이 하나만 있고 응용 프로그램을 만드는 경우에만 모듈 이름을 암시적으로 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="6b9ff-128">*액세스 가능성 한정자* 는, `private`, `internal`중 하나일 수 있습니다. `public`</span><span class="sxs-lookup"><span data-stu-id="6b9ff-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="6b9ff-129">자세한 내용은 [Access Control](access-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="6b9ff-130">기본값은 public입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="6b9ff-131">모듈의 코드 참조</span><span class="sxs-lookup"><span data-stu-id="6b9ff-131">Referencing Code in Modules</span></span>

<span data-ttu-id="6b9ff-132">다른 모듈에서 함수, 형식 및 값을 참조 하는 경우 정규화 된 이름을 사용 하거나 모듈을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="6b9ff-133">정규화 된 이름을 사용 하는 경우 네임 스페이스, 모듈 및 원하는 프로그램 요소에 대 한 식별자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="6b9ff-134">다음과 같이 정규화 된 경로의 각 부분을 점 (.)으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="6b9ff-135">모듈 또는 하나 이상의 네임 스페이스를 열어 코드를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="6b9ff-136">네임 스페이스 및 모듈을 여 [는 `open` ](import-declarations-the-open-keyword.md)방법에 대 한 자세한 내용은 Import 선언: 키워드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="6b9ff-137">다음 코드 예제에서는 파일의 끝까지 모든 코드를 포함 하는 최상위 모듈을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="6b9ff-138">동일한 프로젝트의 다른 파일에서이 코드를 사용 하려면 다음 예제와 같이 함수를 사용 하기 전에 정규화 된 이름을 사용 하거나 모듈을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="6b9ff-139">중첩 모듈</span><span class="sxs-lookup"><span data-stu-id="6b9ff-139">Nested Modules</span></span>

<span data-ttu-id="6b9ff-140">모듈은 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-140">Modules can be nested.</span></span> <span data-ttu-id="6b9ff-141">내부 모듈은 새 모듈이 아니라 내부 모듈 임을 나타내기 위해 바깥쪽 모듈 선언 만큼 바깥쪽으로 들여쓰기 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="6b9ff-142">예를 들어 다음 두 예제를 비교해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-142">For example, compare the following two examples.</span></span> <span data-ttu-id="6b9ff-143">모듈 `Z` 은 다음 코드의 내부 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="6b9ff-144">그러나 모듈 `Z` 은 다음 코드의 형제의 `Y` to module입니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="6b9ff-145">모듈 `Z` 은 모듈 `Y`의 다른 선언과 같이 들여쓰기 되지 않으므로 다음 코드의 형제 모듈 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="6b9ff-146">마지막으로, 외부 모듈에 선언이 없고 다른 모듈 선언 바로 뒤에 오는 경우 새 모듈 선언이 내부 모듈로 간주 되지만 두 번째 모듈 정의가 첫 번째 모듈 정의 보다 더 많이 들여쓰기 되지 않으면 컴파일러에서 경고를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="6b9ff-147">이 경고를 제거 하려면 내부 모듈을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="6b9ff-148">파일의 모든 코드를 하나의 외부 모듈에 포함 하 고 내부 모듈을 원하는 경우 외부 모듈은 등호를 요구 하지 않고 외부 모듈에 포함 되는 모든 내부 모듈 선언을 포함 한 선언을 들여쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="6b9ff-149">내부 모듈 선언 내의 선언을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="6b9ff-150">다음 코드에서는이 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="6b9ff-151">재귀 모듈</span><span class="sxs-lookup"><span data-stu-id="6b9ff-151">Recursive modules</span></span>

<span data-ttu-id="6b9ff-152">F # 4.1에는 포함 된 모든 코드를 상호 재귀적으로 사용할 수 있는 모듈의 개념이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="6b9ff-153">이 작업은를 `module rec`통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-153">This is done via `module rec`.</span></span>  <span data-ttu-id="6b9ff-154">를 사용 `module rec` 하면 형식 및 모듈 간에 상호 참조 코드를 작성할 수 없는 일부 pains을 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="6b9ff-155">이에 대 한 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
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

<span data-ttu-id="6b9ff-156">예외 `DontSqueezeTheBananaException` 와 클래스 `Banana` 는 둘 다 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="6b9ff-157">또한 모듈과 `BananaHelpers` 클래스가 `Banana` 서로를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="6b9ff-158">`RecursiveModule` 모듈에서 키워드를 `rec` 제거한 경우 F #을 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="6b9ff-159">이 기능은 F # 4.1를 사용 하는 [네임 스페이스](namespaces.md) 에서도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b9ff-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b9ff-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b9ff-160">See also</span></span>

- [<span data-ttu-id="6b9ff-161">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="6b9ff-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6b9ff-162">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="6b9ff-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="6b9ff-163">F # RFC FS-1009-파일 내에서 더 큰 범위에 대해 상호 참조 형식 및 모듈 허용</span><span class="sxs-lookup"><span data-stu-id="6b9ff-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
