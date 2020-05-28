---
title: Main()과 명령줄 인수 - C# 프로그래밍 가이드
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 723884dd448232777ae2cfeac5bfcf5ea24363b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007743"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="23862-102">Main()과 명령줄 인수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="23862-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="23862-103">`Main` 메서드는 C# 애플리케이션의 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="23862-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="23862-104">(라이브러리와 서비스에는 `Main` 메서드가 진입점으로 필요하지 않습니다.) 애플리케이션이 시작될 때 `Main` 메서드는 호출되는 첫 번째 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="23862-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

<span data-ttu-id="23862-105">C# 프로그램에는 하나의 진입점만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="23862-106">`Main` 메서드가 있는 클래스가 둘 이상 있는 경우 `-main` 컴파일러 옵션으로 프로그램을 컴파일하여 진입점으로 사용할 `Main` 메서드를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23862-106">If you have more than one class that has a `Main` method, you must compile your program with the `-main` compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="23862-107">자세한 내용은 [-main(C# 컴파일러 옵션)](../../language-reference/compiler-options/main-compiler-option.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23862-107">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="23862-108">개요</span><span class="sxs-lookup"><span data-stu-id="23862-108">Overview</span></span>

- <span data-ttu-id="23862-109">`Main` 메서드는 실행 가능한 프로그램의 진입점으로, 프로그램의 제어가 시작되고 끝나는 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="23862-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="23862-110">`Main`은 클래스 또는 구조체 내부에 선언됩니다</span><span class="sxs-lookup"><span data-stu-id="23862-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="23862-111">`Main`은 [정적](../../language-reference/keywords/static.md)이어야 하며 [공용](../../language-reference/keywords/public.md)일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-111">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="23862-112">(앞의 예제에서는 기본 액세스 권한 [개인](../../language-reference/keywords/private.md)을 받습니다.) 바깥쪽 클래스 또는 구조체는 정적일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-112">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="23862-113">`Main`에는 `void` 또는 `int`를 가지고 있거나 C# 7.1로 시작하거나 `Task` 또는 `Task<int>` 반환 형식을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="23862-114">`Main`에서 `Task` 또는 `Task<int>`을 반환하는 경우에만 `Main` 선언에 [`async`](../../language-reference/keywords/async.md) 한정자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="23862-115">이는 구체적으로 `async void Main` 메서드를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="23862-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="23862-116">`Main` 메서드는 명령줄 인수를 포함하는 `string[]` 매개 변수 사용 여부에 관계 없이 선언될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="23862-117">Visual Studio를 사용하여 Windows 애플리케이션을 만드는 경우 매개 변수를 수동으로 추가하거나 <xref:System.Environment.GetCommandLineArgs> 메서드를 사용하여 [명령줄 인수](command-line-arguments.md)를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23862-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="23862-118">매개 변수는 0부터 시작하는 명령줄 인수로 읽힙니다.</span><span class="sxs-lookup"><span data-stu-id="23862-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="23862-119">C 및 C++와 달리, 프로그램의 이름이 `args` 배열의 첫 번째 명령줄 인수로 처리되지 않지만, <xref:System.Environment.GetCommandLineArgs> 메서드의 첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="23862-119">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="23862-120">다음은 유효한 `Main` 시그니처 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="23862-120">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="23862-121">앞의 예에서는 모두 공용 접근자 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23862-121">The preceding examples all use the public accessor modifier.</span></span> <span data-ttu-id="23862-122">일반적으로 그렇게 하지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="23862-122">That is typical, but not required.</span></span>

<span data-ttu-id="23862-123">`async` 및 `Task`, `Task<int>` 반환 형식을 추가하면 콘솔 애플리케이션을 시작해야 하고 비동기 작업을 `Main`에서 `await`해야 하는 경우에 프로그램 코드가 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="23862-123">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="23862-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="23862-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="23862-125">참조</span><span class="sxs-lookup"><span data-stu-id="23862-125">See also</span></span>

- [<span data-ttu-id="23862-126">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="23862-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="23862-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="23862-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="23862-128">메서드</span><span class="sxs-lookup"><span data-stu-id="23862-128">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="23862-129">C# 프로그램 내부</span><span class="sxs-lookup"><span data-stu-id="23862-129">Inside a C# Program</span></span>](../inside-a-program/index.md)
