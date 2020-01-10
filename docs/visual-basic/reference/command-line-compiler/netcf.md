---
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
ms.openlocfilehash: 7f14ce07a2928f4dbffd3aa57f8cdd514b75694c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716709"
---
# <a name="-netcf"></a><span data-ttu-id="d83bc-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="d83bc-102">-netcf</span></span>

<span data-ttu-id="d83bc-103">.NET Compact Framework를 대상으로 하는 컴파일러를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-103">Sets the compiler to target the .NET Compact Framework.</span></span>

## <a name="syntax"></a><span data-ttu-id="d83bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="d83bc-104">Syntax</span></span>

```console
-netcf
```

## <a name="remarks"></a><span data-ttu-id="d83bc-105">주의</span><span class="sxs-lookup"><span data-stu-id="d83bc-105">Remarks</span></span>

<span data-ttu-id="d83bc-106">`-netcf` 옵션을 설정 하면 Visual Basic 컴파일러가 전체 .NET Framework 아닌 .NET Compact Framework를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-106">The `-netcf` option causes the Visual Basic compiler to target the .NET Compact Framework rather than the full .NET Framework.</span></span> <span data-ttu-id="d83bc-107">전체 .NET Framework에만 표시 되는 언어 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-107">Language functionality that is present only in the full .NET Framework is disabled.</span></span>

<span data-ttu-id="d83bc-108">`-netcf` 옵션은 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)와 함께 사용할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="d83bc-109">`-netcf`에서 사용 하지 않도록 설정 된 언어 기능은 `-sdkpath`대상으로 지정 된 파일에 없는 언어 기능과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="d83bc-110">`-netcf` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="d83bc-111">`-netcf` 옵션은 Visual Basic 장치 프로젝트가 로드 될 때 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="d83bc-112">`-netcf` 옵션은 다음과 같은 언어 기능을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="d83bc-113">프로그램의 실행을 종료 하는 [End \<keyword > Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 키워드는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="d83bc-114">다음 프로그램은 `-netcf` 없이 컴파일되고 실행 되지만 `-netcf`를 사용 하 여 컴파일 타임에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="d83bc-115">런타임에 바인딩은 모든 폼에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="d83bc-116">컴파일 시간 오류는 인식 되는 런타임에 바인딩 시나리오가 발견 될 때 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="d83bc-117">다음 프로그램은 `-netcf` 없이 컴파일되고 실행 되지만 `-netcf`를 사용 하 여 컴파일 타임에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="d83bc-118">[Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)및 [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md) 한정자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="d83bc-119">[Declare 문의](../../../visual-basic/language-reference/statements/declare-statement.md) 구문도 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`으로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="d83bc-120">다음 코드는 컴파일에 `-netcf`의 효과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="d83bc-121">Visual Basic에서 제거 된 Visual Basic 6.0 키워드를 사용 하면 `-netcf`를 사용할 때 다른 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="d83bc-122">이는 다음 키워드에 대 한 오류 메시지에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="d83bc-123">예</span><span class="sxs-lookup"><span data-stu-id="d83bc-123">Example</span></span>

<span data-ttu-id="d83bc-124">다음 코드는 C 드라이브에 있는 .NET Compact Framework의 기본 설치 디렉터리에 있는 mscorlib.dll 및 Microsoft.visualbasic 버전을 사용 하 여 .NET Compact Framework `Myfile.vb` 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-124">The following code compiles `Myfile.vb` with the .NET Compact Framework, using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the .NET Compact Framework on the C drive.</span></span> <span data-ttu-id="d83bc-125">일반적으로 .NET Compact Framework의 최신 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d83bc-125">Typically, you would use the most recent version of the .NET Compact Framework.</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="d83bc-126">참조</span><span class="sxs-lookup"><span data-stu-id="d83bc-126">See also</span></span>

- [<span data-ttu-id="d83bc-127">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d83bc-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d83bc-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="d83bc-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="d83bc-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="d83bc-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
