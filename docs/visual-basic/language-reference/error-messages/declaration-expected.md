---
title: 선언이 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 64ee75c93615f57b15fea29f06fff500a395ba0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803833"
---
# <a name="declaration-expected"></a><span data-ttu-id="305df-102">선언이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="305df-102">Declaration expected</span></span>
<span data-ttu-id="305df-103">할당 또는 루프 문과 같은 선언문이 아닌 문을 프로시저 외부에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="305df-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="305df-104">선언에만 외부 프로시저 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="305df-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="305df-105">또는, 프로그래밍 요소를 선언 하지 선언 키워드와 같은 `Dim` 또는 `Const`합니다.</span><span class="sxs-lookup"><span data-stu-id="305df-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="305df-106">**오류 ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="305df-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="305df-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="305df-107">To correct this error</span></span>  
  
- <span data-ttu-id="305df-108">프로시저의 본문 선언문이 아닌 문을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="305df-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="305df-109">적절 한 선언 키워드로 선언을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="305df-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="305df-110">선언 키워드의 철자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="305df-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="305df-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="305df-111">See also</span></span>

- [<span data-ttu-id="305df-112">절차</span><span class="sxs-lookup"><span data-stu-id="305df-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="305df-113">Dim 문</span><span class="sxs-lookup"><span data-stu-id="305df-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
