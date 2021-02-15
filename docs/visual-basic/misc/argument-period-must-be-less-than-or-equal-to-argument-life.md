---
description: "자세한 정보: ' Period ' 인수는 ' Life ' 인수 보다 작거나 같아야 합니다."
title: "'Period' 인수는 'Life' 인수보다 작거나 같아야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbrFinancial_PeriodLELife
ms.assetid: dc575d41-b376-4b05-bbbe-6de1e98385f1
ms.openlocfilehash: 451defc2e9015b12bd6b340c3c32782ea4d4774f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100458631"
---
# <a name="argument-period-must-be-less-than-or-equal-to-argument-life"></a><span data-ttu-id="36ca5-103">'Period' 인수는 'Life' 인수보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ca5-103">Argument 'Period' must be less than or equal to argument 'Life'</span></span>

<span data-ttu-id="36ca5-104">자산 감가상각이 계산되는 기간을 지정하는 `Period` 인수 값이 `Life` 인수 값보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="36ca5-104">The value of the `Period` argument, which specifies the period for which asset depreciation is calculated, is greater than the value of the `Life` argument.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="36ca5-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="36ca5-105">To correct this error</span></span>  
  
- <span data-ttu-id="36ca5-106">`Life` 와 `Period` 인수는 같은 단위로 표현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ca5-106">Ensure that the `Life` and `Period` arguments are expressed in the same units.</span></span> <span data-ttu-id="36ca5-107">예를 들어 `Life` 가 월 단위로 측정되면 `Period` 도 월 단위로 측정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ca5-107">For example, if `Life` is measured in months, `Period` should be as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ca5-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="36ca5-108">See also</span></span>

- [<span data-ttu-id="36ca5-109">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="36ca5-109">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
