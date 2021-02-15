---
description: "자세히 알아보기: <methodname> 축소 변환 없이 이러한 인수를 사용 하 여 액세스할 수 있는 오버 로드 된 ' '를 호출할 수 없습니다. <list>"
title: <methodname>축소 변환 없이이 인수로 호출할 수 있는 액세스 가능한 오버 로드 된 ' '이 (가) 없습니다. <list>
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousCall2
ms.assetid: 13b20ffa-9f02-4971-a3cb-e08b402fd971
ms.openlocfilehash: a802b420a01c1894feca2c61c0bfdbb7be5104f5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475710"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion-list"></a><span data-ttu-id="ec567-103">\<methodname>축소 변환 없이이 인수로 호출할 수 있는 액세스 가능한 오버 로드 된 ' '이 (가) 없습니다.\<list></span><span class="sxs-lookup"><span data-stu-id="ec567-103">No accessible overloaded '\<methodname>' can be called with these arguments without a narrowing conversion: \<list></span></span>

<span data-ttu-id="ec567-104">오버로드된 메서드를 호출했지만 축소 변환 없이 제공된 인수 목록과 메서드를 일치시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec567-104">An overloaded method was called, but the method cannot be matched with the list of provided arguments without a narrowing conversion.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ec567-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ec567-105">To correct this error</span></span>  
  
1. <span data-ttu-id="ec567-106">`Option Strict Off`을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec567-106">Specify `Option Strict Off`.</span></span>
  
2. <span data-ttu-id="ec567-107">오버로드된 메서드의 서명과 일치하도록 인수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ec567-107">Change the arguments to match a signature of the overloaded method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec567-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ec567-108">See also</span></span>

- [<span data-ttu-id="ec567-109">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="ec567-109">Passing Arguments by Value and by Reference</span></span>](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="ec567-110">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="ec567-110">Widening and Narrowing Conversions</span></span>](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
