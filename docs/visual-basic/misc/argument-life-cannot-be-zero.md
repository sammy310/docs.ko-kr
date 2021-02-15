---
description: "자세한 정보: ' Life ' 인수는 0 일 수 없습니다."
title: "'Life' 인수는 0일 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrFinancial_LifeNEZero
ms.assetid: c402da97-a2b2-4219-a83a-0cebbfdffef2
ms.openlocfilehash: e07c31ab73d6ad3f055adcbf7f4f67d48311c6cd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474878"
---
# <a name="argument-life-cannot-be-zero"></a><span data-ttu-id="48d72-103">'Life' 인수는 0일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="48d72-103">Argument 'Life' cannot be zero</span></span>

<span data-ttu-id="48d72-104">자산의 내용 연수 길이를 지정하는 `Life`이어야 하는 `Double` 에 대한 인수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="48d72-104">An argument for `Life`, which must be a `Double` that specifies the length of useful life of the asset, is not valid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48d72-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="48d72-105">To correct this error</span></span>  
  
- <span data-ttu-id="48d72-106">식에서 인수의 철자를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="48d72-106">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="48d72-107">철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48d72-107">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
- <span data-ttu-id="48d72-108">이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="48d72-108">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d72-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="48d72-109">See also</span></span>

- [<span data-ttu-id="48d72-110">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="48d72-110">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
