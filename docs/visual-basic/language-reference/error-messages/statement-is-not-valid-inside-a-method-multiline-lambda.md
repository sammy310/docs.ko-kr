---
title: 문은은 메서드 / 여러 줄 람다 내부 올바르지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: 994cafc44a37d16d0f70caec560f530c6a836ec0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841565"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="7e58f-102">메서드 내부에는 문을 사용할 수 없습니다./multiline lambda</span><span class="sxs-lookup"><span data-stu-id="7e58f-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="7e58f-103">문 내에서 올바르지 않습니다.는 `Sub`, `Function`, 속성 `Get`, 또는 속성 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7e58f-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="7e58f-104">일부 문이 모듈 또는 클래스 수준에서 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e58f-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="7e58f-105">다른 사용자와 같은 `Option Strict`, 네임 스페이스 수준 이어야 하며 다른 모든 선언 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e58f-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="7e58f-106">**오류 ID:** BC30024</span><span class="sxs-lookup"><span data-stu-id="7e58f-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e58f-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7e58f-107">To correct this error</span></span>  
  
-   <span data-ttu-id="7e58f-108">문을 프로시저에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e58f-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e58f-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="7e58f-109">See also</span></span>

- [<span data-ttu-id="7e58f-110">Sub 문</span><span class="sxs-lookup"><span data-stu-id="7e58f-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="7e58f-111">Function 문</span><span class="sxs-lookup"><span data-stu-id="7e58f-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="7e58f-112">Get 문</span><span class="sxs-lookup"><span data-stu-id="7e58f-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="7e58f-113">Set 문</span><span class="sxs-lookup"><span data-stu-id="7e58f-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
