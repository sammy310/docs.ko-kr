---
description: '자세한 정보: -netcf'
title: -netcf
ms.date: 03/13/2018
f1_keywords:
- /netcf
- -netcf
helpviewer_keywords:
- -netcf compiler option [Visual Basic]
- netcf compiler option [Visual Basic]
- /netcf compiler option [Visual Basic]
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
ms.openlocfilehash: 053e177d8d7008b10bfa552ee60cbbd2d5dda565
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100434916"
---
# <a name="-netcf"></a><span data-ttu-id="43744-103">-netcf</span><span class="sxs-lookup"><span data-stu-id="43744-103">-netcf</span></span>

<span data-ttu-id="43744-104">.NET Compact Framework를 대상으로 하는 컴파일러를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-104">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="43744-105">구문</span><span class="sxs-lookup"><span data-stu-id="43744-105">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="43744-106">설명</span><span class="sxs-lookup"><span data-stu-id="43744-106">Remarks</span></span>

<span data-ttu-id="43744-107">`-netcf` 옵션을 설정하면 Visual Basic 컴파일러가 전체 .NET Framework가 아닌 .NET Compact Framework를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-107">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="43744-108">전체 .NET Framework에만 표시되는 언어 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43744-108">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="43744-109">`-netcf` 옵션은 [-sdkpath](sdkpath.md)와 함께 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="43744-109">The `-netcf` option is designed to be used with [-sdkpath](sdkpath.md).</span></span> <span data-ttu-id="43744-110">`-netcf`에 의해 비활성화된 언어 기능은 `-sdkpath`를 사용하여 대상으로 지정된 파일에 없는 언어 기능과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-110">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="43744-111">Visual Studio 개발 환경 내에서는 `-netcf` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43744-111">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="43744-112">`-netcf` 옵션은 Visual Basic 디바이스 프로젝트가 로드될 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="43744-112">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="43744-113">`-netcf` 옵션은 다음 언어 기능을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-113">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="43744-114">프로그램의 실행을 종료하는 [End \<keyword> Statement](../../language-reference/statements/end-keyword-statement.md) 키워드는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43744-114">The [End \<keyword> Statement](../../language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="43744-115">다음 프로그램은 `-netcf` 없이 컴파일되고 실행되지만 `-netcf`를 사용하면 컴파일 시간에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-115">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="43744-116">런타임에 바인딩은 모든 형태에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43744-116">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="43744-117">런타임에 바인딩 시나리오가 인식되면 컴파일 시간 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="43744-117">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="43744-118">다음 프로그램은 `-netcf` 없이 컴파일되고 실행되지만 `-netcf`를 사용하면 컴파일 시간에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-118">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="43744-119">[Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md) 및 [Unicode](../../language-reference/modifiers/unicode.md) 한정자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43744-119">The [Auto](../../language-reference/modifiers/auto.md), [Ansi](../../language-reference/modifiers/ansi.md), and [Unicode](../../language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="43744-120">[Declare Statement](../../language-reference/statements/declare-statement.md)의 구문도 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`으로 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="43744-120">The syntax of the [Declare Statement](../../language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="43744-121">다음 코드는 컴파일에 대한 `-netcf`의 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43744-121">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="43744-122">Visual Basic에서 제거된 Visual Basic 6.0 키워드를 사용하면 `-netcf`를 사용할 때 다른 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="43744-122">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="43744-123">이는 다음 키워드에 대한 오류 메시지에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43744-123">This affects the error messages for the following keywords:</span></span>

  - `Open`

  - `Close`

  - `Put`

  - `Print`

  - `Write`

  - `Input`

  - `Lock`

  - `Unlock`

  - `Seek`

  - `Width`

  - `Name`

  - `FreeFile`

  - `EOF`

  - `Loc`

  - `LOF`

  - `Line`

## <a name="example"></a><span data-ttu-id="43744-124">예제</span><span class="sxs-lookup"><span data-stu-id="43744-124">Example</span></span>

<span data-ttu-id="43744-125">다음 코드는 C 드라이브의 .NET Compact Framework 기본 설치 디렉터리에 있는 mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 사용하여 .NET Compact Framework로 `Myfile.vb`를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-125">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="43744-126">일반적으로 최신 버전의 .NET Compact Framework를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="43744-126">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="43744-127">참조</span><span class="sxs-lookup"><span data-stu-id="43744-127">See also</span></span>

- [<span data-ttu-id="43744-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="43744-128">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="43744-129">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="43744-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="43744-130">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="43744-130">-sdkpath</span></span>](sdkpath.md)
