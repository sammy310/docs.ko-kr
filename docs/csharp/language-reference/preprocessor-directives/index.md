---
title: C# 전처리기 지시문
ms.date: 07/20/2015
f1_keywords:
- cs.preprocessor
helpviewer_keywords:
- preprocessor directives [C#]
- keywords [C#], preprocessor directives
ms.assetid: f2406090-b244-4f7e-ab72-3698fefed724
ms.openlocfilehash: f63ba3e0bd89a88ad04b14c2f359a8cde65e8f12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "69608604"
---
# <a name="c-preprocessor-directives"></a><span data-ttu-id="25670-102">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="25670-102">C# preprocessor directives</span></span>
<span data-ttu-id="25670-103">이 단원에서는 다음 C# 전처리기 지시문에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25670-103">This section contains information about the following C# preprocessor directives:</span></span>

- [<span data-ttu-id="25670-104">#if</span><span class="sxs-lookup"><span data-stu-id="25670-104">#if</span></span>](./preprocessor-if.md)
- [<span data-ttu-id="25670-105">#else</span><span class="sxs-lookup"><span data-stu-id="25670-105">#else</span></span>](./preprocessor-else.md)
- [<span data-ttu-id="25670-106">#elif</span><span class="sxs-lookup"><span data-stu-id="25670-106">#elif</span></span>](./preprocessor-elif.md)
- [<span data-ttu-id="25670-107">#endif</span><span class="sxs-lookup"><span data-stu-id="25670-107">#endif</span></span>](./preprocessor-endif.md)
- [<span data-ttu-id="25670-108">#define</span><span class="sxs-lookup"><span data-stu-id="25670-108">#define</span></span>](./preprocessor-define.md)
- [<span data-ttu-id="25670-109">#undef</span><span class="sxs-lookup"><span data-stu-id="25670-109">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="25670-110">#warning</span><span class="sxs-lookup"><span data-stu-id="25670-110">#warning</span></span>](./preprocessor-warning.md)
- [<span data-ttu-id="25670-111">#error</span><span class="sxs-lookup"><span data-stu-id="25670-111">#error</span></span>](./preprocessor-error.md)
- [<span data-ttu-id="25670-112">#line</span><span class="sxs-lookup"><span data-stu-id="25670-112">#line</span></span>](./preprocessor-line.md)
- [<span data-ttu-id="25670-113">#region</span><span class="sxs-lookup"><span data-stu-id="25670-113">#region</span></span>](./preprocessor-region.md)
- [<span data-ttu-id="25670-114">#endregion</span><span class="sxs-lookup"><span data-stu-id="25670-114">#endregion</span></span>](./preprocessor-endregion.md)
- [<span data-ttu-id="25670-115">#pragma</span><span class="sxs-lookup"><span data-stu-id="25670-115">#pragma</span></span>](./preprocessor-pragma.md)
- [<span data-ttu-id="25670-116">#pragma warning</span><span class="sxs-lookup"><span data-stu-id="25670-116">#pragma warning</span></span>](./preprocessor-pragma-warning.md)
- [<span data-ttu-id="25670-117">#pragma checksum</span><span class="sxs-lookup"><span data-stu-id="25670-117">#pragma checksum</span></span>](./preprocessor-pragma-checksum.md)

<span data-ttu-id="25670-118">자세한 내용과 예제는 각 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25670-118">See the individual topics for more information and examples.</span></span>

<span data-ttu-id="25670-119">컴파일러에는 별도의 전처리기가 없지만, 이 단원에 설명된 지시문은 전처리기가 있는 것처럼 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="25670-119">Although the compiler doesn't have a separate preprocessor, the directives described in this section are processed as if there were one.</span></span> <span data-ttu-id="25670-120">지시문은 조건부 컴파일에서 지원하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25670-120">They are used to help in conditional compilation.</span></span> <span data-ttu-id="25670-121">C 및 C++ 지시문과 달리, 매크로를 만들기 위해 이러한 지시문을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25670-121">Unlike C and C++ directives, you cannot use these directives to create macros.</span></span>

<span data-ttu-id="25670-122">전처리기 지시문은 한 줄에서 유일한 명령이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25670-122">A preprocessor directive must be the only instruction on a line.</span></span>

## <a name="see-also"></a><span data-ttu-id="25670-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25670-123">See also</span></span>

- [<span data-ttu-id="25670-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="25670-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="25670-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="25670-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
