---
title: Alias 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 84c8f39e632eebbe5382492669820910b38bc360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839745"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="7ab2d-102">Alias 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ab2d-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="7ab2d-103">외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ab2d-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ab2d-104">설명</span><span class="sxs-lookup"><span data-stu-id="7ab2d-104">Remarks</span></span>  
 <span data-ttu-id="7ab2d-105">`Alias` 키워드는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ab2d-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="7ab2d-106">Declare 문</span><span class="sxs-lookup"><span data-stu-id="7ab2d-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="7ab2d-107">다음 예제에서는 `Alias` 키워드 advapi32.dll에서 함수의 이름을 제공 하는 데 사용 됩니다 `GetUserNameA`는 `getUserName` 이 예에서 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ab2d-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="7ab2d-108">함수 `getUserName` sub 라고 `getUser`, 현재 사용자의 이름을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ab2d-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="7ab2d-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ab2d-109">See also</span></span>

- [<span data-ttu-id="7ab2d-110">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="7ab2d-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
