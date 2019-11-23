---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005288"
---
# <a name="-quiet"></a><span data-ttu-id="730df-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="730df-102">-quiet</span></span>

<span data-ttu-id="730df-103">컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="730df-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="730df-104">구문</span><span class="sxs-lookup"><span data-stu-id="730df-104">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="730df-105">주의</span><span class="sxs-lookup"><span data-stu-id="730df-105">Remarks</span></span>

<span data-ttu-id="730df-106">기본적으로 `-quiet`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730df-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="730df-107">컴파일러가 구문 관련 오류 또는 경고를 보고 하면 소스 코드의 줄도 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="730df-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="730df-108">컴파일러 출력을 구문 분석 하는 응용 프로그램의 경우 컴파일러에서 진단 텍스트만 출력 하는 것이 더 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730df-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="730df-109">다음 예제에서 `Module1`는 `-quiet`없이 컴파일될 때 소스 코드를 포함 하는 오류를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="730df-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="730df-110">출력:</span><span class="sxs-lookup"><span data-stu-id="730df-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="730df-111">`-quiet`를 사용 하 여 컴파일하면 컴파일러는 다음만 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="730df-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="730df-112">`-quiet` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="730df-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="730df-113">예제</span><span class="sxs-lookup"><span data-stu-id="730df-113">Example</span></span>

<span data-ttu-id="730df-114">다음 코드는 `T2.vb` 컴파일되고 구문 관련 컴파일러 진단에 대 한 코드를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="730df-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="730df-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="730df-115">See also</span></span>

- [<span data-ttu-id="730df-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="730df-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="730df-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="730df-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
