---
title: "'Class' 문은 짝이 되는 'End Class'로 끝나야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 559595e9902ec2f0a19fd6b13e2c89fa1c2b52d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602410"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="cff33-102">'Class' 문은 짝이 되는 'End Class'로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff33-102">'Class' statement must end with a matching 'End Class'</span></span>
<span data-ttu-id="cff33-103">`Class` 시작 하는 데 사용 되는 `Class` ; 되므로 일치 하는 블록의 시작 부분에만 사용할 수 있습니다 `End Class` 문 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff33-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="cff33-104">중복 된 `Class` 문이 종료 하지 하 `Class` 블록 `End Class`합니다.</span><span class="sxs-lookup"><span data-stu-id="cff33-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="cff33-105">**오류 ID:** BC30481</span><span class="sxs-lookup"><span data-stu-id="cff33-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cff33-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cff33-106">To correct this error</span></span>  
  
- <span data-ttu-id="cff33-107">불필요한 `Class` 문을 찾아서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cff33-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
- <span data-ttu-id="cff33-108">종료 합니다 `Class` 일치 하는 블록 `End Class`합니다.</span><span class="sxs-lookup"><span data-stu-id="cff33-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff33-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="cff33-109">See also</span></span>

- [<span data-ttu-id="cff33-110">최종 \<키워드 > 문</span><span class="sxs-lookup"><span data-stu-id="cff33-110">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [<span data-ttu-id="cff33-111">Class 문</span><span class="sxs-lookup"><span data-stu-id="cff33-111">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
