---
title: Alias 절
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866680"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="187ad-102">Alias 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="187ad-102">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="187ad-103">외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="187ad-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="187ad-104">설명</span><span class="sxs-lookup"><span data-stu-id="187ad-104">Remarks</span></span>  

 <span data-ttu-id="187ad-105">`Alias`키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="187ad-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="187ad-106">Declare 문</span><span class="sxs-lookup"><span data-stu-id="187ad-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="187ad-107">다음 예제에서는 키워드를 사용 하 여 `Alias` `GetUserNameA` 이 예제에서 대신 사용 되는 advapi32.dll의 함수 이름을 제공 `getUserName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="187ad-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="187ad-108">`getUserName` `getUser` 현재 사용자의 이름을 표시 하는 sub에서 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="187ad-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="187ad-109">참조</span><span class="sxs-lookup"><span data-stu-id="187ad-109">See also</span></span>

- [<span data-ttu-id="187ad-110">키워드</span><span class="sxs-lookup"><span data-stu-id="187ad-110">Keywords</span></span>](../keywords/index.md)
