---
title: "'Dir' 함수는 처음에 'Pathname' 인수를 사용하여 호출해야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767892"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="e3f22-102">'Dir' 함수는 처음에 'Pathname' 인수를 사용하여 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3f22-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="e3f22-103">에 대 한 초기 호출을 `Dir` 함수는 포함 되지 않습니다는 `PathName` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f22-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="e3f22-104">첫 번째 호출은 `Dir` 포함 해야 합니다는 `PathName`, 하지만 후속 호출 `Dir` 다음 항목을 검색 하는 매개 변수를 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3f22-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3f22-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e3f22-105">To correct this error</span></span>  
  
1. <span data-ttu-id="e3f22-106">제공 된 `PathName` 함수 호출의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3f22-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3f22-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3f22-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
