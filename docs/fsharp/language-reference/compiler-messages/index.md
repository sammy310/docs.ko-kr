---
title: 컴파일러 오류 및 경고
description: F# 컴파일러가 내보낼 오류 및 경고에 대한 설명과 해결 방법
ms.date: 12/21/2019
ms.openlocfilehash: 9769ddee989f0774cfae8842e60dbd3fd2065f9c
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190179"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="277ea-103">F# 컴파일러 메시지</span><span class="sxs-lookup"><span data-stu-id="277ea-103">F# compiler messages</span></span>

<span data-ttu-id="277ea-104">이 섹션에서는 F# 컴파일러가 특정 구문에 대해 내보내는 컴파일러 오류 및 경고에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="277ea-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="277ea-105">기본 오류 집합은 다음과 같이 하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="277ea-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="277ea-106">`-warnaserror+` 컴파일러 옵션을 사용하여 특정 경고를 오류로 취급하고</span><span class="sxs-lookup"><span data-stu-id="277ea-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="277ea-107">`-nowarn` 컴파일러 옵션을 사용하여 특정 경고를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="277ea-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="277ea-108">특정 경고나 오류가 아직 이 섹션에 기록되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="277ea-108">If a particular warning or error is not yet recorded in this section:</span></span>

- <span data-ttu-id="277ea-109">이 페이지 끝으로 이동하여 오류 번호나 텍스트를 포함한 피드백을 보내거나</span><span class="sxs-lookup"><span data-stu-id="277ea-109">Go to the end of this page and send feedback that includes the number or text of the error, or</span></span>
- <span data-ttu-id="277ea-110">[create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/main/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx)의 지침에 따라 이 리포지토리에 대한 끌어오기 요청을 열어 직접 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="277ea-110">Add it yourself by following the instructions in [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/main/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) and opening a pull request for this repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="277ea-111">참조</span><span class="sxs-lookup"><span data-stu-id="277ea-111">See also</span></span>

- [<span data-ttu-id="277ea-112">F# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="277ea-112">F# Compiler Options</span></span>](../compiler-options.md)
