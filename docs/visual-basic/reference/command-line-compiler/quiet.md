---
description: '자세한 정보: -quiet'
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
ms.openlocfilehash: 23e1b6472e80ac6ca2ecea5c4390b43722ccebb6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432730"
---
# <a name="-quiet"></a><span data-ttu-id="b6a7b-103">-quiet</span><span class="sxs-lookup"><span data-stu-id="b6a7b-103">-quiet</span></span>

<span data-ttu-id="b6a7b-104">컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-104">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6a7b-105">구문</span><span class="sxs-lookup"><span data-stu-id="b6a7b-105">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="b6a7b-106">설명</span><span class="sxs-lookup"><span data-stu-id="b6a7b-106">Remarks</span></span>

<span data-ttu-id="b6a7b-107">기본적으로 `-quiet`은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-107">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="b6a7b-108">컴파일러가 구문 관련 오류 또는 경고를 보고하면 소스 코드에서 줄도 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-108">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="b6a7b-109">컴파일러 출력을 구문 분석하는 애플리케이션의 경우 컴파일러에서 진단 텍스트만 출력하는 것이 더 편리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-109">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="b6a7b-110">다음 예제에서 `Module1`은 `-quiet` 없이 컴파일될 때 소스 코드가 포함된 오류를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-110">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="b6a7b-111">출력:</span><span class="sxs-lookup"><span data-stu-id="b6a7b-111">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="b6a7b-112">`-quiet`로 컴파일된 컴파일러는 다음 항목만 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-112">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="b6a7b-113">Visual Studio 개발 환경 내에서는 `-quiet` 옵션을 사용할 수 없습니다. 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-113">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="b6a7b-114">예제</span><span class="sxs-lookup"><span data-stu-id="b6a7b-114">Example</span></span>

<span data-ttu-id="b6a7b-115">다음 코드는 `T2.vb`를 컴파일하고 구문 관련 컴파일러 진단을 위한 코드를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a7b-115">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="b6a7b-116">참조</span><span class="sxs-lookup"><span data-stu-id="b6a7b-116">See also</span></span>

- [<span data-ttu-id="b6a7b-117">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="b6a7b-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="b6a7b-118">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="b6a7b-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
