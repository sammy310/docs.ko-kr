---
title: Alias 절
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349142"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="faa9e-102">Alias 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="faa9e-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="faa9e-103">외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="faa9e-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faa9e-104">주의</span><span class="sxs-lookup"><span data-stu-id="faa9e-104">Remarks</span></span>  
 <span data-ttu-id="faa9e-105">이 컨텍스트에서는 `Alias` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa9e-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="faa9e-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="faa9e-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="faa9e-107">다음 예에서는 `Alias` 키워드를 사용 하 여이 예제에서 사용 되는 `getUserName`를 사용 하는 advapi32.dll `GetUserNameA`의 함수 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa9e-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="faa9e-108">함수 `getUserName`은 현재 사용자의 이름을 표시 하는 sub `getUser`에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa9e-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="faa9e-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faa9e-109">See also</span></span>

- [<span data-ttu-id="faa9e-110">키워드</span><span class="sxs-lookup"><span data-stu-id="faa9e-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
