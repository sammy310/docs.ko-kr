---
title: 부울 연산자
description: 사용할 수 있는 부울 연산자에 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: ad4bdd1121389f7e280647dbe0c4d0098ffb17df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641888"
---
# <a name="boolean-operators"></a><span data-ttu-id="856d5-103">부울 연산자</span><span class="sxs-lookup"><span data-stu-id="856d5-103">Boolean Operators</span></span>

<span data-ttu-id="856d5-104">부울 연산자에 대 한 지원에 설명 합니다 F# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="856d5-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="856d5-105">부울 연산자 요약</span><span class="sxs-lookup"><span data-stu-id="856d5-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="856d5-106">다음 표에서 사용할 수 있는 부울 연산자는 F# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="856d5-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="856d5-107">이러한 연산자에서 지 원하는 유일한 형식이 `bool` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="856d5-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="856d5-108">연산자</span><span class="sxs-lookup"><span data-stu-id="856d5-108">Operator</span></span>|<span data-ttu-id="856d5-109">설명</span><span class="sxs-lookup"><span data-stu-id="856d5-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="856d5-110">부정 부울</span><span class="sxs-lookup"><span data-stu-id="856d5-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="856d5-111">부울 OR</span><span class="sxs-lookup"><span data-stu-id="856d5-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="856d5-112">부울 AND</span><span class="sxs-lookup"><span data-stu-id="856d5-112">Boolean AND</span></span>|

<span data-ttu-id="856d5-113">부울 AND 및 OR 연산자를 수행 *평가 단락 (short-circuit)*, 식의 전체 결과 확인 하는 데 필요한 경우에 연산자의 오른쪽에 있는 식 평가, 합니다.</span><span class="sxs-lookup"><span data-stu-id="856d5-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="856d5-114">두 번째 식의 `&&` 연산자는 첫 번째 식이 계산 되는 경우에 계산 됩니다 `true`;의 두 번째 식의 `||` 연산자는 첫 번째 식이 계산 되는 경우에 계산 됩니다 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="856d5-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="856d5-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="856d5-115">See also</span></span>

- [<span data-ttu-id="856d5-116">비트 연산자</span><span class="sxs-lookup"><span data-stu-id="856d5-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="856d5-117">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="856d5-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="856d5-118">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="856d5-118">Symbol and Operator Reference</span></span>](index.md)
