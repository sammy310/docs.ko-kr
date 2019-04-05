---
title: '가져오기 선언: Open 키워드'
description: 에 대해 알아봅니다 F# 선언 및 모듈 또는 네임 스페이스 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 지정 하는 방법을 가져옵니다.
ms.date: 04/04/2019
ms.openlocfilehash: ad64190c3243c57a185f3b864270fca80590f079
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055003"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="c3951-103">가져오기 선언: `open` 키워드</span><span class="sxs-lookup"><span data-stu-id="c3951-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
> <span data-ttu-id="c3951-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="c3951-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="c3951-106">*가져오기 선언* 모듈이 나 네임 스페이스 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="c3951-107">구문</span><span class="sxs-lookup"><span data-stu-id="c3951-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="c3951-108">설명</span><span class="sxs-lookup"><span data-stu-id="c3951-108">Remarks</span></span>

<span data-ttu-id="c3951-109">정규화 된 네임 스페이스 또는 모듈 경로 사용 하 여 코드를 참조 될 때마다 쓰기, 읽기 및 유지 관리 하기 어려운 코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="c3951-110">대신 사용할 수는 `open` 키워드에 대 한 자주 모듈 및 네임 스페이스를 사용 하 여 해당 모듈 또는 네임 스페이스의 멤버를 참조할 때 정규화 된 이름 대신 이름의 약식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="c3951-111">이 키워드는 비슷합니다는 `using` C#의 키워드 `using namespace` Visual c + +에서 및 `Imports` Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="c3951-112">같은 프로젝트 또는 참조 된 프로젝트나 어셈블리에 모듈을 제공 하는 네임 스페이스 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="c3951-113">프로젝트에 대 한 참조를 추가 또는 사용할 수 없는 경우는 `-reference` 명령`-`명령줄 옵션 (또는 해당 약어 `-r`).</span><span class="sxs-lookup"><span data-stu-id="c3951-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="c3951-114">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3951-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="c3951-115">가져오기 선언 바깥쪽 네임 스페이스, 모듈 또는 파일의 끝까지 선언 뒤에 오는 코드를 사용할 수 있는 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="c3951-116">여러 가져오기 선언에 사용 하는 경우 별도 줄에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="c3951-117">다음 코드의 사용을 보여 줍니다.는 `open` 키워드 코드를 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="c3951-118">F# 컴파일러를 내보내지는지 않습니다 오류 또는 경고를 둘 이상 열려 모듈 또는 네임 스페이스 이름이 발생 하면 모호성이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="c3951-119">모호성이 발생 하면 F# 기본 설정 보다 최근에 연 모듈 또는 네임 스페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="c3951-120">예를 들어, 다음 코드에서에서 `empty` 의미 `Seq.empty`경우에 `empty` 둘 다에 `List` 고 `Seq` 모듈.</span><span class="sxs-lookup"><span data-stu-id="c3951-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="c3951-121">따라서 주의 같은 모듈 또는 네임 스페이스를 열 때 `List` 또는 `Seq` 이름이 같더라도; 대신 정규화 된 이름을 사용 하는 것이 좋습니다는 멤버를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="c3951-122">코드는 가져오기 선언의 순서에 종속 된 모든 상황을 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="c3951-123">기본적으로 열려 있는 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="c3951-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="c3951-124">일부 네임 스페이스에서 자주 사용 됩니다 F# 열리는 암시적 선언의 명시적으로 가져올 필요 없이 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="c3951-125">다음 표에서 기본적으로 열려 있는 네임 스페이스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="c3951-126">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c3951-126">Namespace</span></span>|<span data-ttu-id="c3951-127">설명</span><span class="sxs-lookup"><span data-stu-id="c3951-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="c3951-128">기본 포함 F# 와 같은 기본 제공 형식에 대 한 정의 입력 `int` 하 고 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="c3951-129">같은 기본 산술 연산이 포함 되어 있습니다 `+` 고 `*`입니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="c3951-130">변경 불가능 컬렉션 클래스를 같은 포함 `List` 고 `Array`입니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="c3951-131">지연 계산 등 비동기 워크플로 제어 구문에 대 한 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="c3951-132">서식이 지정 된 io와 같은 함수를 포함 합니다 `printf` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="c3951-133">AutoOpen 특성</span><span class="sxs-lookup"><span data-stu-id="c3951-133">AutoOpen Attribute</span></span>

<span data-ttu-id="c3951-134">적용할 수는 `AutoOpen` 어셈블리를 참조할 때 네임 스페이스 또는 모듈을 자동으로 열도록 하려면 특성을 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="c3951-135">적용할 수도 있습니다는 `AutoOpen` 부모 모듈 또는 네임 스페이스를 열 때 해당 모듈을 자동으로 열려면 모듈에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="c3951-136">자세한 내용은 [Core.AutoOpenAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="c3951-137">RequireQualifiedAccess 특성</span><span class="sxs-lookup"><span data-stu-id="c3951-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="c3951-138">일부 모듈, 레코드 또는 공용 구조체 형식을 지정할 수는 `RequireQualifiedAccess` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="c3951-139">이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조할 때 가져오기 선언을 포함 여부에 관계 없이 정규화 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="c3951-140">에 전략적으로이 특성을 사용 하면 일반적으로 정의 하는 형식 이름을 사용한 경우 이름 충돌을 방지 하 고 있으므로 복원 력을 코드 라이브러리의 변경 내용에 도움이 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="c3951-141">자세한 내용은 [Core.RequireQualifiedAccessAttribute 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3951-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3951-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3951-142">See also</span></span>

- [<span data-ttu-id="c3951-143">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c3951-143">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c3951-144">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c3951-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="c3951-145">모듈</span><span class="sxs-lookup"><span data-stu-id="c3951-145">Modules</span></span>](modules.md)
