---
title: "'ReDim'으로 차수를 변경할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 8d80af7682f27b403e0f463fdbebbcac71f18b01
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077373"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="4f8b2-102">'ReDim'으로 차수를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f8b2-102">'ReDim' cannot change the number of dimensions</span></span>

<span data-ttu-id="4f8b2-103">작업에서 `ReDim` 문을 사용하여 배열 차수(차원 수)를 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8b2-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="4f8b2-104">`ReDim` 은 이전에 선언된 배열의 차원 크기를 하나 이상 변경할 수 있지만 배열 차수를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f8b2-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f8b2-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4f8b2-105">To correct this error</span></span>  
  
- <span data-ttu-id="4f8b2-106">해당 차원의 크기가 아닌 배열의 차수를 변경하려는지 확인하고 가능한 경우 `Dim` 을 사용하여 원하는 차수의 새 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4f8b2-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8b2-107">참조</span><span class="sxs-lookup"><span data-stu-id="4f8b2-107">See also</span></span>

- [<span data-ttu-id="4f8b2-108">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="4f8b2-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="4f8b2-109">Visual Basic의 배열 차원</span><span class="sxs-lookup"><span data-stu-id="4f8b2-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="4f8b2-110">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="4f8b2-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="4f8b2-111">Dim 문</span><span class="sxs-lookup"><span data-stu-id="4f8b2-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
