---
title: '선언 가져오기: open 키워드'
description: F# 가져오기 선언에 대해 알아보고 정규화된 이름을 사용하지 않고 참조할 수 있는 요소가 있는 모듈 또는 네임스페이스를 지정하는 방법에 대해 알아봅니다.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021537"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="7c930-103">가져오기 선언: `open` 키워드</span><span class="sxs-lookup"><span data-stu-id="7c930-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="7c930-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="7c930-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="7c930-106">*가져오기 선언은* 정규화된 이름을 사용하지 않고 참조할 수 있는 요소를 지정하는 모듈 또는 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c930-107">구문</span><span class="sxs-lookup"><span data-stu-id="7c930-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="7c930-108">설명</span><span class="sxs-lookup"><span data-stu-id="7c930-108">Remarks</span></span>

<span data-ttu-id="7c930-109">매번 정규화된 네임스페이스 또는 모듈 경로를 사용하여 코드를 참조하면 작성, 읽기 및 유지 관리하기 어려운 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="7c930-110">대신 자주 사용하는 `open` 모듈 및 네임스페이스에 키워드를 사용하여 해당 모듈 또는 네임스페이스의 멤버를 참조할 때 정규화된 이름 대신 짧은 형식의 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="7c930-111">이 키워드는 C#, `using` `using namespace` Visual C++및 Visual Basic의 `Imports` 키워드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="7c930-112">제공된 모듈 또는 네임스페이스는 동일한 프로젝트 또는 참조된 프로젝트 또는 어셈블리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="7c930-113">그렇지 않은 경우 프로젝트에 대한 참조를 추가하거나 `-reference` 명령줄 옵션(또는 `-r`약어)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-113">If it is not, you can add a reference to the project, or use the `-reference` command-line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="7c930-114">자세한 내용은 [컴파일러 옵션을](compiler-options.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c930-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="7c930-115">import 선언은 둘러싸는 네임스페이스, 모듈 또는 파일의 끝까지 선언 다음에 오는 코드에서 이름을 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="7c930-116">여러 가져오기 선언을 사용하는 경우 별도의 줄에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="7c930-117">다음 코드는 코드를 단순화하기 위해 키워드를 `open` 사용하는 방법을 보여 주십니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="7c930-118">F# 컴파일러는 둘 이상의 열린 모듈 또는 네임스페이스에서 동일한 이름이 발생할 때 모호성이 발생할 때 오류 또는 경고를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="7c930-119">모호성이 발생하면 F#은 최근에 열린 모듈 또는 네임스페이스에 우선권을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="7c930-120">예를 들어 다음 코드에서 `empty` `Seq.empty`는 `empty` `List` 와 `Seq` 모듈 모두에 있더라도 을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="7c930-121">따라서 이름이 동일한 멤버를 포함하거나 `List` `Seq` 모듈이나 네임스페이스를 열 때는 주의해야 합니다. 대신 정규화된 이름을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="7c930-122">코드가 가져오기 선언의 순서에 종속되는 상황은 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="7c930-123">기본적으로 열려 있는 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7c930-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="7c930-124">일부 네임스페이스는 F# 코드에서 자주 사용되므로 명시적 가져오기 선언없이 암시적으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="7c930-125">다음 표에는 기본적으로 열려 있는 네임스페이스가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="7c930-126">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7c930-126">Namespace</span></span>|<span data-ttu-id="7c930-127">설명</span><span class="sxs-lookup"><span data-stu-id="7c930-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="7c930-128">`int` 와 `float`같은 기본 제공 형식에 대한 기본 F# 형식 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="7c930-129">`+` 및 와 `*`같은 기본 산술 연산을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="7c930-130">`List` 와 같은 변경할 수 없는 `Array`컬렉션 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="7c930-131">지연 평가 및 비동기 워크플로와 같은 제어 구문에 대한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="7c930-132">함수와 같이 서식이 지정된 IO에 대한 함수를 `printf` 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="7c930-133">자동 열기 특성</span><span class="sxs-lookup"><span data-stu-id="7c930-133">AutoOpen Attribute</span></span>

<span data-ttu-id="7c930-134">어셈블리를 `AutoOpen` 참조할 때 네임스페이스 또는 모듈을 자동으로 열려면 어셈블리에 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="7c930-135">상위 모듈 또는 `AutoOpen` 네임스페이스가 열릴 때 모듈에 특성을 적용하여 해당 모듈을 자동으로 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="7c930-136">자세한 내용은 [Core.AutoOpenAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c930-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="7c930-137">요구정규어특성액세스 특성</span><span class="sxs-lookup"><span data-stu-id="7c930-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="7c930-138">일부 모듈, 레코드 또는 공용 구조체 형식은 특성을 지정할 `RequireQualifiedAccess` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="7c930-139">이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조할 때 가져오기 선언을 포함하는지 여부에 관계없이 정규화된 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="7c930-140">일반적으로 사용되는 이름을 정의하는 형식에서 이 특성을 전략적으로 사용하는 경우 이름 충돌을 방지하고 라이브러리의 변경 사항에 대한 코드 복원력을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c930-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="7c930-141">자세한 내용은 [Core.RequireQualifiedAccess속성 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7c930-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c930-142">참조</span><span class="sxs-lookup"><span data-stu-id="7c930-142">See also</span></span>

- [<span data-ttu-id="7c930-143">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="7c930-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="7c930-144">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7c930-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="7c930-145">모듈</span><span class="sxs-lookup"><span data-stu-id="7c930-145">Modules</span></span>](modules.md)
