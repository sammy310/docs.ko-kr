---
title: 이 배열은 고정되었거나 임시로 잠겨 있습니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c74d9524ff64101ba6002e133b93c9b80e8f50a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337970"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="57b35-102">이 배열은 고정되었거나 임시로 잠겨 있습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="57b35-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="57b35-103">이 오류는 다음과 같은 가능한 원인을:</span><span class="sxs-lookup"><span data-stu-id="57b35-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="57b35-104">사용 하 여 `ReDim` 고정 크기 배열 요소의 수를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b35-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="57b35-105">하나의 요소가 전달 인수로 프로시저에는 모듈 수준 동적 배열 차원을 다시 지정 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b35-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="57b35-106">배열 방지 하기 위해 잠겨 요소를 전달 하면 프로시저 내의 참조 매개 변수에 대 한 메모리 할당을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b35-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="57b35-107">값을 할당 하려고를 `Variant` 배열을 포함 하는 변수 하지만 `Variant` 현재 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b35-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57b35-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="57b35-108">To correct this error</span></span>  
  
1. <span data-ttu-id="57b35-109">원래 배열을 사용 하 여 선언 하 여 고정 되지 않고 동적으로 만들 `ReDim` (경우 배열의 선언 된 프로시저 내에서) 또는 (배열 모듈 수준에서 선언 됩니다 경우 요소의 수를 지정 하지 않고 선언 하 여.</span><span class="sxs-lookup"><span data-stu-id="57b35-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="57b35-110">실제로 프로시저 모듈에서 모두 표시 되므로 요소를 전달 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b35-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="57b35-111">잠그고 어떤 결정을 `Variant` 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="57b35-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b35-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="57b35-112">See also</span></span>

- [<span data-ttu-id="57b35-113">배열</span><span class="sxs-lookup"><span data-stu-id="57b35-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
