---
description: "자세한 정보: ' ReDim '은 맨 오른쪽 차원만 변경할 수 있습니다."
title: "'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
ms.openlocfilehash: 6816e5b2e9c7c079b78ce53e168f46b337831512
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454692"
---
# <a name="redim-can-only-change-the-right-most-dimension"></a><span data-ttu-id="922f9-103">'ReDim'으로는 맨 오른쪽 차원만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="922f9-103">'ReDim' can only change the right-most dimension</span></span>

<span data-ttu-id="922f9-104">`ReDim` 문에서 `Preserve` 키워드를 사용하여 마지막 차원이 아닌 배열의 차원을 변경하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="922f9-104">A `ReDim` statement attempted to use the `Preserve` keyword to change a dimension of an array that is not the last dimension.</span></span> <span data-ttu-id="922f9-105">`Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="922f9-105">When using `Preserve`, you can resize only the last dimension of an array.</span></span> <span data-ttu-id="922f9-106">다른 모든 차원의 경우 기존 배열과 동일한 크기를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="922f9-106">For all other dimensions, you must specify the same size as for the existing array.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="922f9-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="922f9-107">To correct this error</span></span>  
  
- <span data-ttu-id="922f9-108">`Preserve` 키워드를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="922f9-108">Remove the `Preserve` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="922f9-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="922f9-109">See also</span></span>

- [<span data-ttu-id="922f9-110">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="922f9-110">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="922f9-111">Visual Basic의 배열 차원</span><span class="sxs-lookup"><span data-stu-id="922f9-111">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="922f9-112">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="922f9-112">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="922f9-113">Dim 문</span><span class="sxs-lookup"><span data-stu-id="922f9-113">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
