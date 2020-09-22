---
title: 오버플로가 발생했습니다(Visual Basic 런타임 오류).
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: e287d6c24eca75d8bf20181a201056f467d6fc4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871227"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="d1a9b-102">오버플로가 발생했습니다(Visual Basic 런타임 오류).</span><span class="sxs-lookup"><span data-stu-id="d1a9b-102">Overflow (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="d1a9b-103">할당 대상의 제한을 초과 하는 할당을 시도할 때 오버플로가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a9b-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1a9b-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d1a9b-104">To correct this error</span></span>  
  
1. <span data-ttu-id="d1a9b-105">할당, 계산 및 데이터 형식 변환 결과가 너무 커서 해당 값 유형에 허용 되는 변수 범위 내에 표시 되지 않도록 하 고 필요한 경우 더 큰 범위의 값을 보유할 수 있는 유형의 변수에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a9b-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="d1a9b-106">속성에 대 한 할당이 속성의 범위에 맞게 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a9b-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="d1a9b-107">정수로 강제 변환 된 계산에 사용 되는 숫자의 결과가 정수 보다 크지 않은지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1a9b-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a9b-108">참조</span><span class="sxs-lookup"><span data-stu-id="d1a9b-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="d1a9b-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d1a9b-109">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="d1a9b-110">오류 형식</span><span class="sxs-lookup"><span data-stu-id="d1a9b-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
