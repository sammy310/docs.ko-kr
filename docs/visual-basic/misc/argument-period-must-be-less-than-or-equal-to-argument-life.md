---
title: "'Period' 인수는 'Life' 인수보다 작거나 같아야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbrFinancial_PeriodLELife
ms.assetid: dc575d41-b376-4b05-bbbe-6de1e98385f1
ms.openlocfilehash: 844192f1168e6fef7906ffc133dcc3b5ba40b42c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087039"
---
# <a name="argument-period-must-be-less-than-or-equal-to-argument-life"></a><span data-ttu-id="62ae8-102">'Period' 인수는 'Life' 인수보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ae8-102">Argument 'Period' must be less than or equal to argument 'Life'</span></span>

<span data-ttu-id="62ae8-103">자산 감가상각이 계산되는 기간을 지정하는 `Period` 인수 값이 `Life` 인수 값보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="62ae8-103">The value of the `Period` argument, which specifies the period for which asset depreciation is calculated, is greater than the value of the `Life` argument.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="62ae8-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="62ae8-104">To correct this error</span></span>  
  
- <span data-ttu-id="62ae8-105">`Life` 와 `Period` 인수는 같은 단위로 표현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ae8-105">Ensure that the `Life` and `Period` arguments are expressed in the same units.</span></span> <span data-ttu-id="62ae8-106">예를 들어 `Life` 가 월 단위로 측정되면 `Period` 도 월 단위로 측정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ae8-106">For example, if `Life` is measured in months, `Period` should be as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ae8-107">참조</span><span class="sxs-lookup"><span data-stu-id="62ae8-107">See also</span></span>

- [<span data-ttu-id="62ae8-108">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="62ae8-108">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
