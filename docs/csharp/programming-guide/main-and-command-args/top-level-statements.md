---
title: 최상위 문 - C# 프로그래밍 가이드
description: C# 9 이상의 최상위 문에 대해 알아봅니다.
ms.date: 03/08/2021
helpviewer_keywords:
- C# language, top-level statements
- C# language, Main method
ms.openlocfilehash: 69ff5fd606f5e12f55bd3e6dfc15fc7e64d8352b
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190451"
---
# <a name="top-level-statements-c-programming-guide"></a><span data-ttu-id="a2944-103">최상위 문(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a2944-103">Top-level statements (C# Programming Guide)</span></span>

<span data-ttu-id="a2944-104">C# 9부터 콘솔 애플리케이션 프로젝트에 `Main` 메서드를 명시적으로 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-104">Starting in C# 9, you don't have to explicitly include a `Main` method in a console application project.</span></span> <span data-ttu-id="a2944-105">대신 *최상위 문* 기능을 사용하여 작성해야 하는 코드를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-105">Instead, you can use the *top-level statements* feature to minimize the code you have to write.</span></span> <span data-ttu-id="a2944-106">이 경우 컴파일러는 애플리케이션에 대한 클래스 및 `Main` 메서드 진입점을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-106">In this case, the compiler generates a class and `Main` method entry point for the application.</span></span>

<span data-ttu-id="a2944-107">다음은 C# 9의 완전한 C# 프로그램인 *Program.cs* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-107">Here's a *Program.cs* file that is a complete C# program in C# 9:</span></span>

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

<span data-ttu-id="a2944-108">최상위 문을 사용하면 Azure Functions 및 GitHub Actions와 같은 소규모 유틸리티에 대한 간단한 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-108">Top-level statements let you write simple programs for small utilities such as Azure Functions and GitHub Actions.</span></span> <span data-ttu-id="a2944-109">또한 새로운 C# 프로그래머가 코드를 학습하고 작성하는 작업을 더 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-109">They also make it simpler for new C# programmers to get started learning and writing code.</span></span>

<span data-ttu-id="a2944-110">다음 섹션에서는 최상위 문으로 수행할 수 있는 작업과 수행할 수 없는 작업에 대한 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-110">The following sections explain the rules on what you can and can't do with top-level statements.</span></span>

## <a name="only-one-top-level-file"></a><span data-ttu-id="a2944-111">하나의 최상위 파일만</span><span class="sxs-lookup"><span data-stu-id="a2944-111">Only one top-level file</span></span>

<span data-ttu-id="a2944-112">애플리케이션에는 진입점이 하나만 있어야 하므로 프로젝트에는 최상위 문이 있는 파일이 하나만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-112">An application must have only one entry point, so a project can have only one file with top-level statements.</span></span> <span data-ttu-id="a2944-113">프로젝트의 두 개 이상의 파일에 최상위 문을 넣으면 다음과 같은 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-113">Putting top-level statements in more than one file in a project results in the following compiler error:</span></span>

> <span data-ttu-id="a2944-114">CS8802 하나의 컴파일 단위만 최상위 문을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-114">CS8802 Only one compilation unit can have top-level statements.</span></span>

<span data-ttu-id="a2944-115">프로젝트에는 최상위 문이 없는 추가 소스 코드 파일이 얼마든지 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-115">A project can have any number of additional source code files that don't have top-level statements.</span></span>

## <a name="no-other-entry-points"></a><span data-ttu-id="a2944-116">다른 진입점 없음</span><span class="sxs-lookup"><span data-stu-id="a2944-116">No other entry points</span></span>

<span data-ttu-id="a2944-117">`Main` 메서드를 명시적으로 작성할 수 있지만 진입점으로 작동할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-117">You can write a `Main` method explicitly, but it can't function as an entry point.</span></span> <span data-ttu-id="a2944-118">컴파일러에서 다음과 같은 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-118">The compiler issues the following warning:</span></span>

> <span data-ttu-id="a2944-119">CS7022 프로그램의 진입점은 전역 코드이며 'Main()' 진입점은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-119">CS7022 The entry point of the program is global code; ignoring 'Main()' entry point.</span></span>

<span data-ttu-id="a2944-120">최상위 문이 있는 프로젝트에서는 프로젝트에 하나 이상의 `Main` 메서드가 있는 경우에도 [-main](../../language-reference/compiler-options/main-compiler-option.md) 컴파일러 옵션을 사용하여 진입점을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-120">In a project with top-level statements, you can't use the [-main](../../language-reference/compiler-options/main-compiler-option.md) compiler option to select the entry point, even if the project has one or more `Main` methods.</span></span>

## <a name="using-directives"></a><span data-ttu-id="a2944-121">`using` 지시문</span><span class="sxs-lookup"><span data-stu-id="a2944-121">`using` directives</span></span>

<span data-ttu-id="a2944-122">using 지시문을 포함하는 경우 다음 예제와 같이 파일에서 먼저 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-122">If you include using directives, they must come first in the file, as in this example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-1/Program.cs":::

## <a name="global-namespace"></a><span data-ttu-id="a2944-123">전역 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a2944-123">Global namespace</span></span>

<span data-ttu-id="a2944-124">최상위 문은 전역 네임스페이스에서 암시적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-124">Top-level statements are implicitly in the global namespace.</span></span>

## <a name="namespaces-and-type-definitions"></a><span data-ttu-id="a2944-125">네임스페이스 및 형식 정의</span><span class="sxs-lookup"><span data-stu-id="a2944-125">Namespaces and type definitions</span></span>

<span data-ttu-id="a2944-126">최상위 문이 있는 파일에는 네임스페이스 및 형식 정의도 포함될 수 있지만 최상위 문 뒤에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-126">A file with top-level statements can also contain namespaces and type definitions, but they must come after the top-level statements.</span></span> <span data-ttu-id="a2944-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-127">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-2/Program.cs":::

## `args`

<span data-ttu-id="a2944-128">최상위 문은 `args` 변수를 참조하여 입력된 명령줄 인수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-128">Top-level statements can reference the `args` variable to access any command-line arguments that were entered.</span></span> <span data-ttu-id="a2944-129">`args` 변수는 null이 아니지만 명령줄 인수가 제공되지 않은 경우 `Length`는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-129">The `args` variable is never null but its `Length` is zero if no command-line arguments were provided.</span></span> <span data-ttu-id="a2944-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-130">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-3/Program.cs":::

## `await`

<span data-ttu-id="a2944-131">`await`를 사용하여 비동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-131">You can call an async method by using `await`.</span></span> <span data-ttu-id="a2944-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-132">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-4/Program.cs":::

## <a name="exit-code-for-the-process"></a><span data-ttu-id="a2944-133">프로세스의 종료 코드</span><span class="sxs-lookup"><span data-stu-id="a2944-133">Exit code for the process</span></span>

<span data-ttu-id="a2944-134">애플리케이션 종료될 때 `int` 값을 반환하려면 `int`를 반환하는 `Main` 메서드에서와 같이 `return` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-134">To return an `int` value when the application ends, use the `return` statement as you would in a `Main` method that returns an `int`.</span></span> <span data-ttu-id="a2944-135">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-135">For example:</span></span>

:::code language="csharp" source="snippets/top-level-statements-5/Program.cs":::

## <a name="implicit-entry-point-method"></a><span data-ttu-id="a2944-136">암시적 진입점 메서드</span><span class="sxs-lookup"><span data-stu-id="a2944-136">Implicit entry point method</span></span>

<span data-ttu-id="a2944-137">컴파일러는 최상위 문이 있는 프로젝트의 프로그램 진입점 역할을 하는 메서드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-137">The compiler generates a method to serve as the program entry point for a project with top-level statements.</span></span> <span data-ttu-id="a2944-138">이 메서드의 이름은 실제로 `Main`이 아니라 코드에서 직접 참조할 수 없는 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-138">The name of this method isn't actually `Main`, it's an implementation detail that your code can't reference directly.</span></span> <span data-ttu-id="a2944-139">메서드의 서명은 최상위 문에 `await` 키워드 또는 `return` 문이 포함되어 있는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-139">The signature of the method depends on whether the top-level statements contain the `await` keyword or the `return` statement.</span></span> <span data-ttu-id="a2944-140">다음 표에서는 편의를 위해 표에 있는 메서드 이름 `Main`을 사용하여 메서드 서명이 어떻게 표시되는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-140">The following table shows what the method signature would look like, using the method name `Main` in the table for convenience.</span></span>

| <span data-ttu-id="a2944-141">최상위 코드에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2944-141">Top-level code contains</span></span>| <span data-ttu-id="a2944-142">암시적 `Main` 서명</span><span class="sxs-lookup"><span data-stu-id="a2944-142">Implicit `Main` signature</span></span>                    |
|------------------------|----------------------------------------------|
| <span data-ttu-id="a2944-143">`await` 및 `return`</span><span class="sxs-lookup"><span data-stu-id="a2944-143">`await` and `return`</span></span>   | `static async Task<int> Main(string[] args)` |
| `await`                | `static async Task Main(string[] args)`      |
| `return`               | `static int Main(string[] args)`             |
| <span data-ttu-id="a2944-144">`await` 또는 `return` 없음</span><span class="sxs-lookup"><span data-stu-id="a2944-144">No `await` or `return`</span></span> | `static void Main(string[] args)`            |

## <a name="c-language-specification"></a><span data-ttu-id="a2944-145">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a2944-145">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
[<span data-ttu-id="a2944-146">최상위 문</span><span class="sxs-lookup"><span data-stu-id="a2944-146">Top-level statements</span></span>](~/_csharplang/proposals/csharp-9.0/top-level-statements.md)

## <a name="see-also"></a><span data-ttu-id="a2944-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2944-147">See also</span></span>

- [<span data-ttu-id="a2944-148">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a2944-148">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a2944-149">메서드</span><span class="sxs-lookup"><span data-stu-id="a2944-149">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="a2944-150">C# 프로그램 내부</span><span class="sxs-lookup"><span data-stu-id="a2944-150">Inside a C# Program</span></span>](../inside-a-program/index.md)
