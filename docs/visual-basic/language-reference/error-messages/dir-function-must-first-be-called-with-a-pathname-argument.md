---
title: "'Dir' 함수는 처음에 'Pathname' 인수를 사용하여 호출해야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1a5d6ed145199ae995a98b6c1180fa3aedf9942c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834161"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="7df4d-102">'Dir' 함수는 처음에 'Pathname' 인수를 사용하여 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="7df4d-103">에 대 한 초기 호출을 `Dir` 함수는 포함 되지 않습니다는 `PathName` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="7df4d-104">첫 번째 호출은 `Dir` 포함 해야 합니다는 `PathName`, 하지만 후속 호출 `Dir` 다음 항목을 검색 하는 매개 변수를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7df4d-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7df4d-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="7df4d-106">제공 된 `PathName` 함수 호출의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="7df4d-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df4d-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="7df4d-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
