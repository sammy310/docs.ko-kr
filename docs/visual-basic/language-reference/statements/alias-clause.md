---
description: '자세한 정보: Alias 절 (Visual Basic)'
title: Alias 절
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: bf0ee1c22105b29aedb99ce45a99ba866f4b93c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674079"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="4b7ec-103">Alias 절(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b7ec-103">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="4b7ec-104">외부 프로시저의 DLL에 다른 이름이 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ec-104">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b7ec-105">설명</span><span class="sxs-lookup"><span data-stu-id="4b7ec-105">Remarks</span></span>  

 <span data-ttu-id="4b7ec-106">`Alias`키워드는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ec-106">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="4b7ec-107">Declare 문</span><span class="sxs-lookup"><span data-stu-id="4b7ec-107">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="4b7ec-108">다음 예제에서는 키워드를 사용 하 여 `Alias` `GetUserNameA` 이 예제에서 대신 사용 되는 advapi32.dll의 함수 이름을 제공 `getUserName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ec-108">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="4b7ec-109">`getUserName` `getUser` 현재 사용자의 이름을 표시 하는 sub에서 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b7ec-109">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="4b7ec-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b7ec-110">See also</span></span>

- [<span data-ttu-id="4b7ec-111">C++ 키워드</span><span class="sxs-lookup"><span data-stu-id="4b7ec-111">Keywords</span></span>](../keywords/index.md)
