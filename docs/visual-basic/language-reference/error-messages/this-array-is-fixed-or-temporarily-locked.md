---
title: 이 배열은 고정되었거나 임시로 잠겨 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350779"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="d0fbb-102">이 배열은 고정되었거나 임시로 잠겨 있습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="d0fbb-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="d0fbb-103">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="d0fbb-104">`ReDim`를 사용 하 여 고정 크기 배열의 요소 수를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="d0fbb-105">Redimensioning 한 요소가 프로시저에 인수로 전달 된 모듈 수준 동적 배열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="d0fbb-106">요소가 전달 되 면 프로시저 내에서 참조 매개 변수에 대 한 메모리 할당 취소를 방지 하기 위해 배열이 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="d0fbb-107">배열이 포함 된 `Variant` 변수에 값을 할당 하려고 하지만 `Variant` 현재 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0fbb-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d0fbb-108">To correct this error</span></span>  
  
1. <span data-ttu-id="d0fbb-109">배열을 프로시저 내에 선언 하는 경우에는 `ReDim`를 사용 하 여 선언 하거나, 배열을 모듈 수준에서 선언 하는 경우 요소 수를 지정 하지 않고 선언 하 여 (배열을 고정 하지 않고 동적으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="d0fbb-110">모듈의 모든 프로시저 내에 표시 되므로 요소를 전달 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="d0fbb-111">`Variant`를 잠그고 있는지 확인 하 고 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0fbb-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fbb-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="d0fbb-112">See also</span></span>

- [<span data-ttu-id="d0fbb-113">배열</span><span class="sxs-lookup"><span data-stu-id="d0fbb-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
