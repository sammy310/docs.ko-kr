---
title: 선언이 필요합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 237622d0dc6c57f66d402f491a6191a5911574e2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409740"
---
# <a name="declaration-expected"></a><span data-ttu-id="a40d3-102">선언이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d3-102">Declaration expected</span></span>
<span data-ttu-id="a40d3-103">대입 또는 loop 문과 같은 비 선언적 문은 프로시저 외부에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d3-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="a40d3-104">프로시저 외부에는 선언만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a40d3-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="a40d3-105">또는와 같은 선언 키워드 없이 프로그래밍 요소가 선언 되었습니다 `Dim` `Const` .</span><span class="sxs-lookup"><span data-stu-id="a40d3-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="a40d3-106">**오류 ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="a40d3-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a40d3-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a40d3-107">To correct this error</span></span>  
  
- <span data-ttu-id="a40d3-108">비 선언적 문을 프로시저 본문으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d3-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="a40d3-109">적절 한 선언 키워드를 사용 하 여 선언을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d3-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="a40d3-110">선언 키워드의 철자가 잘못 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a40d3-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40d3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a40d3-111">See also</span></span>

- [<span data-ttu-id="a40d3-112">절차</span><span class="sxs-lookup"><span data-stu-id="a40d3-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a40d3-113">Dim 문</span><span class="sxs-lookup"><span data-stu-id="a40d3-113">Dim Statement</span></span>](../statements/dim-statement.md)
