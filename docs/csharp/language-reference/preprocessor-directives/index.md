---
description: C# 전처리기 지시문
title: C# 전처리기 지시문
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: a7ffca8b39f1bd9f05193bccbb6d90e67fa262c9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132367"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="db9da-103">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="db9da-103">C# preprocessor directives</span></span>
<span data-ttu-id="db9da-104">이 단원에서는 다음 C# 전처리기 지시문에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="db9da-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="db9da-105">#if</span><span class="sxs-lookup"><span data-stu-id="db9da-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="db9da-106">#else</span><span class="sxs-lookup"><span data-stu-id="db9da-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="db9da-107">#elif</span><span class="sxs-lookup"><span data-stu-id="db9da-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="db9da-108">#endif</span><span class="sxs-lookup"><span data-stu-id="db9da-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="db9da-109">#define</span><span class="sxs-lookup"><span data-stu-id="db9da-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="db9da-110">#undef</span><span class="sxs-lookup"><span data-stu-id="db9da-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="db9da-111">#warning</span><span class="sxs-lookup"><span data-stu-id="db9da-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="db9da-112">#error</span><span class="sxs-lookup"><span data-stu-id="db9da-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="db9da-113">#line</span><span class="sxs-lookup"><span data-stu-id="db9da-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="db9da-114">#region</span><span class="sxs-lookup"><span data-stu-id="db9da-114">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="db9da-115">#endregion</span><span class="sxs-lookup"><span data-stu-id="db9da-115">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="db9da-116">#pragma</span><span class="sxs-lookup"><span data-stu-id="db9da-116">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="db9da-117">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="db9da-117">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="db9da-118">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="db9da-118">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="db9da-119">자세한 내용과 예제는 각 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db9da-119">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="db9da-120">컴파일러에는 별도의 전처리기가 없지만, 이 단원에 설명된 지시문은 전처리기가 있는 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="db9da-120">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="db9da-121">지시문은 조건부 컴파일에서 지원하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db9da-121">They are used to help in conditional compilation.</span></span> <span data-ttu-id="db9da-122">C 및 C++ 지시문과 달리, 매크로를 만들기 위해 이러한 지시문을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db9da-122">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="db9da-123">전처리기 지시문은 한 줄에서 유일한 명령이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9da-123">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="db9da-124">참조</span><span class="sxs-lookup"><span data-stu-id="db9da-124">See also</span></span>

- [<span data-ttu-id="db9da-125">C# 참조</span><span class="sxs-lookup"><span data-stu-id="db9da-125">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="db9da-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="db9da-126">C# Programming Guide</span></span>](../../programming-guide/index.md)
