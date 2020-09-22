---
title: "'Class' 문은 짝이 되는 'End Class'로 끝나야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: d67f0e71dbdbf97420ec5b5ba4b6f06acfba1bd9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874615"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="08355-102">'Class' 문은 짝이 되는 'End Class'로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08355-102">'Class' statement must end with a matching 'End Class'</span></span>

<span data-ttu-id="08355-103">`Class` 는 블록을 시작 하는 데 사용 되므로 블록의 시작 부분에만 나타날 수 있으며 블록을 종료 하는 짝이 되는 `Class` 문을 사용 합니다 `End Class` .</span><span class="sxs-lookup"><span data-stu-id="08355-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="08355-104">중복 문이 있거나를 사용 하 여 `Class` 블록을 종료 하지 않았습니다 `Class` `End Class` .</span><span class="sxs-lookup"><span data-stu-id="08355-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="08355-105">**오류 ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="08355-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08355-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="08355-106">To correct this error</span></span>  
  
- <span data-ttu-id="08355-107">불필요한 `Class` 문을 찾아서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="08355-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
- <span data-ttu-id="08355-108">일치 하 `Class` 는를 사용 하 여 블록을 끝냅니다 `End Class` .</span><span class="sxs-lookup"><span data-stu-id="08355-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08355-109">참조</span><span class="sxs-lookup"><span data-stu-id="08355-109">See also</span></span>

- [<span data-ttu-id="08355-110">End \<keyword> 문</span><span class="sxs-lookup"><span data-stu-id="08355-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="08355-111">Class 문</span><span class="sxs-lookup"><span data-stu-id="08355-111">Class Statement</span></span>](../statements/class-statement.md)
