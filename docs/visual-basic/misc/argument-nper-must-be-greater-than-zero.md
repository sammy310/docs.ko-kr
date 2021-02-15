---
description: "자세한 정보: ' NPer ' 인수는 0 보다 커야 합니다."
title: "'NPer' 인수는 0보다 커야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: ece5e775e2f05f757b2af53594c626f5a023161e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433410"
---
# <a name="argument-nper-must-be-greater-than-zero"></a><span data-ttu-id="87a10-103">'NPer' 인수는 0보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a10-103">Argument 'NPer' must be greater than zero</span></span>

<span data-ttu-id="87a10-104">일정 기간의 고정 지불액과 고정 이자율을 기준으로 연금의 기간 수를 지정하는 `NPer` 을 반환하는 `Double` 함수에는 0보다 큰 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87a10-104">The `NPer` function, which returns a `Double` specifying the number of periods for an annuity based on periodic fixed payments and a fixed interest rate, requires an argument greater than zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="87a10-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="87a10-105">To correct this error</span></span>  
  
- <span data-ttu-id="87a10-106">식에서 인수의 철자를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="87a10-106">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="87a10-107">철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87a10-107">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
- <span data-ttu-id="87a10-108">이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="87a10-108">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a10-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="87a10-109">See also</span></span>

- [<span data-ttu-id="87a10-110">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="87a10-110">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
