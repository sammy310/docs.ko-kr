---
title: "'Period' 인수는 'Life' 인수보다 작거나 같아야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbrFinancial_PeriodLELife
ms.assetid: dc575d41-b376-4b05-bbbe-6de1e98385f1
ms.openlocfilehash: 0b20bb1fd1c0954e30262dd3a3b43d145226b7cc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84367726"
---
# <a name="argument-period-must-be-less-than-or-equal-to-argument-life"></a><span data-ttu-id="adacb-102">'Period' 인수는 'Life' 인수보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adacb-102">Argument 'Period' must be less than or equal to argument 'Life'</span></span>
<span data-ttu-id="adacb-103">자산 감가상각이 계산되는 기간을 지정하는 `Period` 인수 값이 `Life` 인수 값보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="adacb-103">The value of the `Period` argument, which specifies the period for which asset depreciation is calculated, is greater than the value of the `Life` argument.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="adacb-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="adacb-104">To correct this error</span></span>  
  
- <span data-ttu-id="adacb-105">`Life` 와 `Period` 인수는 같은 단위로 표현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adacb-105">Ensure that the `Life` and `Period` arguments are expressed in the same units.</span></span> <span data-ttu-id="adacb-106">예를 들어 `Life` 가 월 단위로 측정되면 `Period` 도 월 단위로 측정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adacb-106">For example, if `Life` is measured in months, `Period` should be as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adacb-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adacb-107">See also</span></span>

- [<span data-ttu-id="adacb-108">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="adacb-108">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
