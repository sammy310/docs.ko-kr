---
description: "자세한 정보: ' ReDim ' 차원 수를 변경할 수 없습니다."
title: "'ReDim'으로 차수를 변경할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: 4552dd6b1cce54813b57e5b8c76a3580b81b8def
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454640"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="85fda-103">'ReDim'으로 차수를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85fda-103">'ReDim' cannot change the number of dimensions</span></span>

<span data-ttu-id="85fda-104">작업에서 `ReDim` 문을 사용하여 배열 차수(차원 수)를 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fda-104">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="85fda-105">`ReDim` 은 이전에 선언된 배열의 차원 크기를 하나 이상 변경할 수 있지만 배열 차수를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85fda-105">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85fda-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="85fda-106">To correct this error</span></span>  
  
- <span data-ttu-id="85fda-107">해당 차원의 크기가 아닌 배열의 차수를 변경하려는지 확인하고 가능한 경우 `Dim` 을 사용하여 원하는 차수의 새 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="85fda-107">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fda-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="85fda-108">See also</span></span>

- [<span data-ttu-id="85fda-109">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="85fda-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="85fda-110">Visual Basic의 배열 차원</span><span class="sxs-lookup"><span data-stu-id="85fda-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="85fda-111">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="85fda-111">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="85fda-112">Dim 문</span><span class="sxs-lookup"><span data-stu-id="85fda-112">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
