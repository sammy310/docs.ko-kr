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
ms.openlocfilehash: d7c3bcba8e62d62904ed778a48d0e8ae6738ce00
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480770"
---
# <a name="-netcf"></a><span data-ttu-id="e0f6e-102">-netcf</span><span class="sxs-lookup"><span data-stu-id="e0f6e-102">-netcf</span></span>

<span data-ttu-id="e0f6e-103">[!INCLUDE[Compact](~/includes/compact-md.md)]를 대상으로 하도록 컴파일러를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-103">Sets the compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>

## <a name="syntax"></a><span data-ttu-id="e0f6e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0f6e-104">Syntax</span></span>

```
-netcf
```

## <a name="remarks"></a><span data-ttu-id="e0f6e-105">설명</span><span class="sxs-lookup"><span data-stu-id="e0f6e-105">Remarks</span></span>

<span data-ttu-id="e0f6e-106">합니다 `-netcf` 옵션을 사용 하면 대상에 Visual Basic 컴파일러는 [!INCLUDE[Compact](~/includes/compact-md.md)] 전체 대신 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-106">The `-netcf` option causes the Visual Basic compiler to target the [!INCLUDE[Compact](~/includes/compact-md.md)] rather than the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e0f6e-107">전체에만 존재 하는 언어 기능이 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-107">Language functionality that is present only in the full [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is disabled.</span></span>

<span data-ttu-id="e0f6e-108">합니다 `-netcf` 옵션은 사용 하도록 설계 되었습니다 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-108">The `-netcf` option is designed to be used with [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).</span></span> <span data-ttu-id="e0f6e-109">사용 하지 않도록 설정 하는 언어 기능 `-netcf` 동일한 언어 기능을 사용 하 여 대상 파일에 없는 `-sdkpath`합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-109">The language features disabled by `-netcf` are the same language features not present in the files targeted with `-sdkpath`.</span></span>

> [!NOTE]
> <span data-ttu-id="e0f6e-110">`-netcf` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-110">The `-netcf` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="e0f6e-111">`-netcf` Visual Basic 장치 프로젝트를 로드 하면 옵션이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-111">The `-netcf` option is set when a Visual Basic device project is loaded.</span></span>

<span data-ttu-id="e0f6e-112">`-netcf` 다음 언어 기능을 변경 하는 옵션:</span><span class="sxs-lookup"><span data-stu-id="e0f6e-112">The `-netcf` option changes the following language features:</span></span>

- <span data-ttu-id="e0f6e-113">합니다 [끝 \<키워드 > 문을](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 프로그램의 실행을 종료 하는 키워드를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-113">The [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) keyword, which terminates execution of a program, is disabled.</span></span> <span data-ttu-id="e0f6e-114">다음 프로그램 없이 컴파일 및 실행 `-netcf` 컴파일 시 실패 하지만 `-netcf`합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-114">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/netcf.vb#34)]

- <span data-ttu-id="e0f6e-115">모든 양식에서 런타임에 바인딩을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-115">Late binding, in all forms, is disabled.</span></span> <span data-ttu-id="e0f6e-116">인식 된 런타임에 바인딩된 시나리오 발생 하는 경우 컴파일 타임 오류가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-116">Compile-time errors are generated when recognized late-binding scenarios are encountered.</span></span> <span data-ttu-id="e0f6e-117">다음 프로그램 없이 컴파일 및 실행 `-netcf` 컴파일 시 실패 하지만 `-netcf`합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-117">The following program compiles and runs without `-netcf` but fails at compile time with `-netcf`.</span></span>

  [!code-vb[VbVbalrCompiler#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#35)]

- <span data-ttu-id="e0f6e-118">합니다 [자동](../../../visual-basic/language-reference/modifiers/auto.md)를 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), 및 [유니코드](../../../visual-basic/language-reference/modifiers/unicode.md) 한정자는 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-118">The [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md), and [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) modifiers are disabled.</span></span> <span data-ttu-id="e0f6e-119">구문의 합니다 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) 로 문 수정 됩니다 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-119">The syntax of the [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) statement is also modified to `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`.</span></span> <span data-ttu-id="e0f6e-120">다음 코드의 결과 보여 줍니다. `-netcf` 를 컴파일할 때.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-120">The following code shows the effect of `-netcf` on a compilation.</span></span>

  [!code-vb[VbVbalrCompiler#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#36)]

- <span data-ttu-id="e0f6e-121">Visual Basic에서 제거 된 Visual Basic 6.0 키워드를 사용 하 여 다른 오류를 생성 하면 `-netcf` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-121">Using Visual Basic 6.0 keywords that were removed from Visual Basic generates a different error when `-netcf` is used.</span></span> <span data-ttu-id="e0f6e-122">이 키워드에 대 한 오류 메시지를 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-122">This affects the error messages for the following keywords:</span></span>

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

## <a name="example"></a><span data-ttu-id="e0f6e-123">예제</span><span class="sxs-lookup"><span data-stu-id="e0f6e-123">Example</span></span>

<span data-ttu-id="e0f6e-124">다음 코드에서는 `Myfile.vb` 사용 하 여 합니다 [!INCLUDE[Compact](~/includes/compact-md.md)]의 기본 설치 디렉터리에서 찾을 mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전을 사용 하는 [!INCLUDE[Compact](~/includes/compact-md.md)] C 드라이브에 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-124">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="e0f6e-125">최신 버전의 사용은 일반적으로 [!INCLUDE[Compact](~/includes/compact-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f6e-125">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>

```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb
```

## <a name="see-also"></a><span data-ttu-id="e0f6e-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0f6e-126">See also</span></span>

- [<span data-ttu-id="e0f6e-127">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="e0f6e-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e0f6e-128">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="e0f6e-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="e0f6e-129">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="e0f6e-129">-sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
