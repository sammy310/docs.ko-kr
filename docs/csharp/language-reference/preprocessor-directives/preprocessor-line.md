---
title: '#line - C# 참조'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: 79033fa652af62c76d54737fbf0a0b47cf3aae99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712496"
---
# <a name="line-c-reference"></a><span data-ttu-id="c0177-102">#line(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c0177-102">#line (C# Reference)</span></span>

<span data-ttu-id="c0177-103">`#line`을 사용하면 오류 및 경고에 대한 컴파일러의 줄 번호 매기기 및 파일 이름 출력(선택 사항)을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-103">`#line` lets you modify the compiler's line numbering and (optionally) the file name output for errors and warnings.</span></span>

<span data-ttu-id="c0177-104">다음 예제에서는 줄 번호와 관련된 두 개의 경고를 보고하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-104">The following example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="c0177-105">`#line 200` 지시문은 다음 줄 번호를 강제로 200(기본값은 #6임)으로 설정하며, 다음 `#line` 지시문까지 파일 이름이 “Special”로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-105">The `#line 200` directive forces the next line's number to be 200 (although the default is #6), and until the next `#line` directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="c0177-106">`#line default` 지시문은 줄 번호 매기기를 기본 번호 매기기로 되돌립니다. 이 경우 이전 지시문을 통해 번호가 다시 매겨진 줄이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-106">The `#line default` directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

<span data-ttu-id="c0177-107">컴파일은 다음 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-107">Compilation produces the following output:</span></span>

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a><span data-ttu-id="c0177-108">설명</span><span class="sxs-lookup"><span data-stu-id="c0177-108">Remarks</span></span>

<span data-ttu-id="c0177-109">`#line` 지시문은 빌드 프로세스의 자동화된 중간 단계에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-109">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="c0177-110">예를 들어 원래 소스 코드 파일에서 줄이 제거되었지만 여전히 컴파일러에서 파일의 원래 줄 번호 매기기에 따라 출력을 생성하려는 경우, 줄을 제거한 다음 `#line`을 사용하여 원래 줄 번호 매기기를 시뮬레이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-110">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>

<span data-ttu-id="c0177-111">`#line hidden` 지시문은 개발자가 코드를 단계별로 실행할 때 `#line hidden`과 다음 `#line` 지시문(다른 `#line hidden` 지시문이 아니라고 가정) 사이에 있는 모든 줄이 프로시저 단위로 실행되도록 디버거에서 연속되는 줄을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-111">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="c0177-112">이 옵션을 사용하여 ASP.NET이 사용자 정의 코드와 컴퓨터에서 생성된 코드를 구분하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-112">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="c0177-113">ASP.NET이 이 기능의 주 소비자지만 기능을 사용할 소스 생성기가 늘어날 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-113">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>

<span data-ttu-id="c0177-114">`#line hidden` 지시문은 오류 보고의 파일 이름이나 줄 번호에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-114">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="c0177-115">즉, 숨겨진 블록에서 오류가 발생할 경우 컴파일러는 오류의 현재 파일 이름과 줄 번호를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-115">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>

<span data-ttu-id="c0177-116">`#line filename` 지시문은 컴파일러 출력에 표시하려는 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-116">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="c0177-117">기본적으로 소스 코드 파일의 실제 이름이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-117">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="c0177-118">파일 이름은 큰따옴표(“ ”)로 묶어야 하고 줄 번호 뒤에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-118">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>

<span data-ttu-id="c0177-119">소스 코드 파일에 `#line` 지시문을 개수와 관계없이 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-119">A source code file can have any number of `#line` directives.</span></span>

## <a name="example-1"></a><span data-ttu-id="c0177-120">예제 1</span><span class="sxs-lookup"><span data-stu-id="c0177-120">Example 1</span></span>

<span data-ttu-id="c0177-121">다음 예제에서는 디버거가 코드의 숨겨진 줄을 어떻게 무시하는지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-121">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="c0177-122">예제를 실행하면 세 줄의 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-122">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="c0177-123">그러나 예제와 같이 중단점을 설정하고 F10 키를 눌러 코드를 단계별로 실행할 경우 디버거는 숨겨진 줄을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-123">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="c0177-124">숨겨진 줄에 중단점을 설정한 경우에도 디버거가 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="c0177-124">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="c0177-125">참조</span><span class="sxs-lookup"><span data-stu-id="c0177-125">See also</span></span>

- [<span data-ttu-id="c0177-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c0177-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c0177-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c0177-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c0177-128">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="c0177-128">C# Preprocessor Directives</span></span>](./index.md)
