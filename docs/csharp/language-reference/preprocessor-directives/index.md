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
ms.openlocfilehash: 1269522b2687b76292f7b796a4ffc8095f23442e
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099063"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="5e17f-103">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="5e17f-103">C# preprocessor directives</span></span>

<span data-ttu-id="5e17f-104">이 단원에서는 다음 C# 전처리기 지시문에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5e17f-104">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="5e17f-105">#if</span><span class="sxs-lookup"><span data-stu-id="5e17f-105">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="5e17f-106">#else</span><span class="sxs-lookup"><span data-stu-id="5e17f-106">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="5e17f-107">#elif</span><span class="sxs-lookup"><span data-stu-id="5e17f-107">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="5e17f-108">#endif</span><span class="sxs-lookup"><span data-stu-id="5e17f-108">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="5e17f-109">#define</span><span class="sxs-lookup"><span data-stu-id="5e17f-109">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="5e17f-110">#undef</span><span class="sxs-lookup"><span data-stu-id="5e17f-110">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="5e17f-111">#warning</span><span class="sxs-lookup"><span data-stu-id="5e17f-111">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="5e17f-112">#error</span><span class="sxs-lookup"><span data-stu-id="5e17f-112">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="5e17f-113">#line</span><span class="sxs-lookup"><span data-stu-id="5e17f-113">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="5e17f-114">#nullable</span><span class="sxs-lookup"><span data-stu-id="5e17f-114">#nullable</span></span>](./preprocessor-nullable.md)
- [<span data-ttu-id="5e17f-115">#region</span><span class="sxs-lookup"><span data-stu-id="5e17f-115">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="5e17f-116">#endregion</span><span class="sxs-lookup"><span data-stu-id="5e17f-116">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="5e17f-117">#pragma</span><span class="sxs-lookup"><span data-stu-id="5e17f-117">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="5e17f-118">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="5e17f-118">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="5e17f-119">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="5e17f-119">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="5e17f-120">자세한 내용과 예제는 각 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e17f-120">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="5e17f-121">컴파일러에는 별도의 전처리기가 없지만, 이 단원에 설명된 지시문은 전처리기가 있는 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e17f-121">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="5e17f-122">지시문은 조건부 컴파일에서 지원하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e17f-122">They are used to help in conditional compilation.</span></span> <span data-ttu-id="5e17f-123">C 및 C++ 지시문과 달리, 매크로를 만들기 위해 이러한 지시문을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e17f-123">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="5e17f-124">전처리기 지시문은 한 줄에서 유일한 명령이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e17f-124">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e17f-125">참조</span><span class="sxs-lookup"><span data-stu-id="5e17f-125">See also</span></span>

- [<span data-ttu-id="5e17f-126">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5e17f-126">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5e17f-127">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5e17f-127">C# Programming Guide</span></span>](../../programming-guide/index.md)
