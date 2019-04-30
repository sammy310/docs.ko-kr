---
title: 진입점
description: 진입점으로 설정 하는 방법을 알아봅니다는 F# 실행 공식적으로 시작 하는 실행 파일로 컴파일된 프로그램입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 915ab17b9a4fc7fd4d0ae344cb273b1d348a02f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996829"
---
# <a name="entry-point"></a><span data-ttu-id="bb0a1-103">진입점</span><span class="sxs-lookup"><span data-stu-id="bb0a1-103">Entry Point</span></span>

<span data-ttu-id="bb0a1-104">이 설명으로 진입점을 설정 하는 데 사용 하는 메서드는 F# 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb0a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="bb0a1-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="bb0a1-106">설명</span><span class="sxs-lookup"><span data-stu-id="bb0a1-106">Remarks</span></span>

<span data-ttu-id="bb0a1-107">이전 구문에서 *let-함수-바인딩에* 함수의 정의 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="bb0a1-108">실행 파일은 실행 공식적으로 시작 되는 컴파일된 프로그램 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="bb0a1-109">에 대 한 진입점을 지정는 F# 적용 하 여 응용 프로그램을 `EntryPoint` 프로그램의 특성 `main` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="bb0a1-110">이 함수 (사용 하 여 만든를 `let` 바인딩) 마지막으로 컴파일된 파일에 마지막 함수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="bb0a1-111">마지막으로 컴파일된 파일은 프로젝트에서 마지막 파일 또는 명령줄에 전달 되는 마지막 파일.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="bb0a1-112">진입점 함수 형식이 `string array -> int`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="bb0a1-113">명령줄에 제공 된 인수에 전달 되는 `main` 문자열 배열에는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="bb0a1-114">배열의 첫 번째 요소는 첫 번째 인수입니다. 실행 파일의 이름은 다른 언어로 이므로 배열에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="bb0a1-115">반환 값은 프로세스에 대 한 종료 코드로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="bb0a1-116">0에는 일반적으로 성공을 나타냅니다. 0이 아닌 값에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="bb0a1-117">규칙은 없습니다 구체적인 의미를 나타내는 0이 아닌 반환 코드입니다. 반환 코드의 의미는 응용 프로그램 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="bb0a1-118">다음 예제에서는 간단한 `main` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="bb0a1-119">명령줄을 사용 하 여이 코드를 실행할 때 `EntryPoint.exe 1 2 3`, 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="bb0a1-120">암시적 진입점</span><span class="sxs-lookup"><span data-stu-id="bb0a1-120">Implicit Entry Point</span></span>

<span data-ttu-id="bb0a1-121">프로그램에 없는 **EntryPoint** 진입점을 컴파일해야 하 고 마지막 파일의 최상위 수준 바인딩을 명시적으로 나타내는 특성의 진입점으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb0a1-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb0a1-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb0a1-122">See also</span></span>

- [<span data-ttu-id="bb0a1-123">함수</span><span class="sxs-lookup"><span data-stu-id="bb0a1-123">Functions</span></span>](index.md)
- [<span data-ttu-id="bb0a1-124">let 바인딩</span><span class="sxs-lookup"><span data-stu-id="bb0a1-124">let Bindings</span></span>](let-bindings.md)