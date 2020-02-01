---
title: 컴파일러 오류 및 경고
description: F# 컴파일러가 내보낼 오류 및 경고에 대 한 설명 및 해결 방법
ms.date: 12/21/2019
ms.openlocfilehash: 52d94475e8b0195281d6244230c50c8f64230aeb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76929656"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="3605d-103">F#컴파일러 메시지</span><span class="sxs-lookup"><span data-stu-id="3605d-103">F# compiler messages</span></span>

<span data-ttu-id="3605d-104">이 섹션에서는 F# 컴파일러가 특정 구문에 대해 내보내는 컴파일러 오류 및 경고에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3605d-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="3605d-105">기본 오류 집합은 다음을 통해 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3605d-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="3605d-106">`-warnaserror+` 컴파일러 옵션을 사용 하 여 오류가 발생 한 것 처럼 특정 경고를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3605d-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="3605d-107">`-nowarn` 컴파일러 옵션을 사용 하 여 특정 경고 무시</span><span class="sxs-lookup"><span data-stu-id="3605d-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="3605d-108">이 섹션에서 특정 경고나 오류가 아직 기록 되지 않은 경우이 페이지의 끝으로 이동 하 여 오류 수 또는 텍스트를 포함 하는 피드백을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3605d-108">If a particular warning or error is not yet recorded in this section, go to the end of this page and send feedback that includes the number or text of the error.</span></span>

## <a name="see-also"></a><span data-ttu-id="3605d-109">참조</span><span class="sxs-lookup"><span data-stu-id="3605d-109">See also</span></span>

- [<span data-ttu-id="3605d-110">F#컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="3605d-110">F# Compiler Options</span></span>](../compiler-options.md)
