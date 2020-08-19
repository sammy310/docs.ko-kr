---
title: '선언 가져오기: open 키워드'
description: 'F # 가져오기 선언과 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 포함 하는 모듈 또는 네임 스페이스를 지정 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 6420df071f86159c44606c2710331d5f587023cc
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557609"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="cc0e6-103">가져오기 선언: `open` 키워드</span><span class="sxs-lookup"><span data-stu-id="cc0e6-103">Import declarations: The `open` keyword</span></span>

<span data-ttu-id="cc0e6-104">*가져오기 선언은* 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 포함 하는 모듈 또는 네임 스페이스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-104">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc0e6-105">구문</span><span class="sxs-lookup"><span data-stu-id="cc0e6-105">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="cc0e6-106">설명</span><span class="sxs-lookup"><span data-stu-id="cc0e6-106">Remarks</span></span>

<span data-ttu-id="cc0e6-107">항상 정규화 된 네임 스페이스 또는 모듈 경로를 사용 하 여 코드를 참조 하면 쓰기, 읽기 및 유지 관리가 어려운 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-107">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="cc0e6-108">대신, `open` 자주 사용 되는 모듈 및 네임 스페이스에 대 한 키워드를 사용 하 여 해당 모듈 또는 네임 스페이스의 멤버를 참조할 때 정규화 된 이름 대신 짧은 형식의 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-108">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="cc0e6-109">이 키워드는 `using` c #의 키워드, `using namespace` Visual C++ 및 Visual Basic와 비슷합니다 `Imports` .</span><span class="sxs-lookup"><span data-stu-id="cc0e6-109">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="cc0e6-110">제공 된 모듈이 나 네임 스페이스는 동일한 프로젝트 또는 참조 된 프로젝트 또는 어셈블리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-110">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="cc0e6-111">그렇지 않은 경우 프로젝트에 대 한 참조를 추가 하거나 `-reference` 명령줄 옵션 또는 해당 약어를 사용할 수 있습니다 `-r` .</span><span class="sxs-lookup"><span data-stu-id="cc0e6-111">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="cc0e6-112">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-112">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="cc0e6-113">가져오기 선언은 선언 뒤에 오는 코드에서 바깥쪽 네임 스페이스, 모듈 또는 파일의 끝까지 이름을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-113">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="cc0e6-114">여러 가져오기 선언을 사용 하는 경우 별도의 줄에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-114">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="cc0e6-115">다음 코드에서는 키워드를 사용 하 여 `open` 코드를 간소화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-115">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="cc0e6-116">두 개 이상의 open 모듈이 나 네임 스페이스에서 같은 이름이 발생할 때 모호성이 발생 하면 F # 컴파일러에서 오류 또는 경고를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-116">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="cc0e6-117">모호성 발생 시 F #은 가장 최근에 열린 모듈 또는 네임 스페이스에 대 한 기본 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-117">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="cc0e6-118">예를 들어, 다음 코드에서 `empty` `Seq.empty` `empty` 는가 및 모듈에 모두 있는 경우에도를 의미 `List` `Seq` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-118">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="cc0e6-119">따라서 같은 이름을 가진 멤버를 포함 하는 또는 같은 모듈 또는 네임 스페이스를 열 때는 주의 해야 `List` `Seq` 합니다. 대신 정규화 된 이름을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-119">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="cc0e6-120">코드가 가져오기 선언의 순서에 따라 달라 지는 상황을 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-120">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="cc0e6-121">기본적으로 열리는 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="cc0e6-121">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="cc0e6-122">일부 네임 스페이스는 명시적 가져오기 선언이 없어도 암시적으로 열리는 F # 코드에서 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-122">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="cc0e6-123">다음 표에서는 기본적으로 열리는 네임 스페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-123">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="cc0e6-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="cc0e6-124">Namespace</span></span>|<span data-ttu-id="cc0e6-125">Description</span><span class="sxs-lookup"><span data-stu-id="cc0e6-125">Description</span></span>|
|---------|-----------|
|`FSharp.Core`|<span data-ttu-id="cc0e6-126">및와 같은 기본 제공 형식에 대 한 기본 F # 형식 정의를 포함 `int` `float` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-126">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`FSharp.Core.Operators`|<span data-ttu-id="cc0e6-127">및와 같은 기본 산술 연산을 `+` 포함 `*` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-127">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`FSharp.Collections`|<span data-ttu-id="cc0e6-128">및와 같은 변경할 수 없는 컬렉션 클래스 `List` 를 포함 `Array` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-128">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`FSharp.Control`|<span data-ttu-id="cc0e6-129">지연 계산, 비동기 워크플로 등의 제어 구문에 대 한 형식을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-129">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`FSharp.Text`|<span data-ttu-id="cc0e6-130">함수와 같은 형식이 지정 된 IO에 대 한 함수를 포함 `printf` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-130">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="cc0e6-131">AutoOpen 특성</span><span class="sxs-lookup"><span data-stu-id="cc0e6-131">AutoOpen Attribute</span></span>

<span data-ttu-id="cc0e6-132">`AutoOpen`어셈블리를 참조할 때 네임 스페이스나 모듈을 자동으로 열려면 어셈블리에 특성을 적용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-132">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="cc0e6-133">`AutoOpen`부모 모듈이 나 네임 스페이스를 열 때 모듈에 특성을 적용 하 여 해당 모듈을 자동으로 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-133">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="cc0e6-134">자세한 내용은 [Autoopenattribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-134">For more information, see [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="cc0e6-135">RequireQualifiedAccess 특성</span><span class="sxs-lookup"><span data-stu-id="cc0e6-135">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="cc0e6-136">일부 모듈, 레코드 또는 공용 구조체 형식에서 특성을 지정할 수 있습니다 `RequireQualifiedAccess` .</span><span class="sxs-lookup"><span data-stu-id="cc0e6-136">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="cc0e6-137">이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조할 때는 가져오기 선언을 포함 하는지 여부에 관계 없이 정규화 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-137">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="cc0e6-138">일반적으로 사용 되는 이름을 정의 하는 형식에 대해이 특성을 사용 하는 경우 이름 충돌을 방지 하 고 라이브러리의 변경에 대 한 코드의 복원 력을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-138">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="cc0e6-139">자세한 내용은 [RequireQualifiedAccessAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0e6-139">For more information, see [RequireQualifiedAccessAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc0e6-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc0e6-140">See also</span></span>

- [<span data-ttu-id="cc0e6-141">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="cc0e6-141">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="cc0e6-142">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="cc0e6-142">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="cc0e6-143">모듈</span><span class="sxs-lookup"><span data-stu-id="cc0e6-143">Modules</span></span>](modules.md)
