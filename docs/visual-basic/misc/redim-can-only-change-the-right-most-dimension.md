---
title: "'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: c3a18bb93d1253628d73919b18fe4614d742d280
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077386"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="3784a-102">'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3784a-102">'ReDim' can only change the right-most dimension</span></span>

<span data-ttu-id="3784a-103">`ReDim` 문에서 `Preserve` 키워드를 사용하여 마지막 차원이 아닌 배열의 차원을 변경하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3784a-103">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="3784a-104">`Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3784a-104">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="3784a-105">다른 모든 차원의 경우 기존 배열과 동일한 크기를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3784a-105">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3784a-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3784a-106">To correct this error</span></span>  
  
- <span data-ttu-id="3784a-107">`Preserve` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3784a-107">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3784a-108">참조</span><span class="sxs-lookup"><span data-stu-id="3784a-108">See also</span></span>

- [<span data-ttu-id="3784a-109">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="3784a-109">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="3784a-110">Visual Basic의 배열 차원</span><span class="sxs-lookup"><span data-stu-id="3784a-110">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="3784a-111">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="3784a-111">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="3784a-112">Dim 문</span><span class="sxs-lookup"><span data-stu-id="3784a-112">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
