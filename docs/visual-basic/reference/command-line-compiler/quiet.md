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
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612591"
---
# <a name="-quiet"></a><span data-ttu-id="de02b-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="de02b-102">-quiet</span></span>

<span data-ttu-id="de02b-103">컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="de02b-104">구문</span><span class="sxs-lookup"><span data-stu-id="de02b-104">Syntax</span></span>

```
-quiet
```

## <a name="remarks"></a><span data-ttu-id="de02b-105">설명</span><span class="sxs-lookup"><span data-stu-id="de02b-105">Remarks</span></span>

<span data-ttu-id="de02b-106">기본적으로 `-quiet`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="de02b-107">컴파일러에서 구문 관련 오류 또는 경고를 보고, 소스 코드에서 줄도 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="de02b-108">컴파일러 출력을 구문 분석 하는 응용 프로그램에 대 한 진단만 텍스트를 출력 하도록 컴파일러에 대 한 편리한 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="de02b-109">다음 예에서 `Module1` 없이 컴파일한 경우 소스 코드를 포함 하는 오류 출력 `-quiet`합니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="de02b-110">출력:</span><span class="sxs-lookup"><span data-stu-id="de02b-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="de02b-111">사용 하 여 컴파일된 `-quiet`, 컴파일러가 다음만 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="de02b-112">`-quiet` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="de02b-113">예제</span><span class="sxs-lookup"><span data-stu-id="de02b-113">Example</span></span>

<span data-ttu-id="de02b-114">다음 코드에서는 `T2.vb` 컴파일러 구문 관련 진단에 대 한 코드를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de02b-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="de02b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="de02b-115">See also</span></span>

- [<span data-ttu-id="de02b-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="de02b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="de02b-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="de02b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
