---
title: 오류 없이 계속됩니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055162"
---
# <a name="resume-without-error"></a><span data-ttu-id="f2628-102">오류 없이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2628-102">Resume without error</span></span>
<span data-ttu-id="f2628-103">`Resume` 문을 오류 처리 코드 외부에 있거나 오류가 없는 경우에 코드 오류 처리기로 점프 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2628-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2628-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f2628-104">To correct this error</span></span>  
  
1. <span data-ttu-id="f2628-105">이동 된 `Resume` 오류 처리기로 문 또는 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2628-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="f2628-106">오류 처리기를 식별 하는 레이블에 대 한 프로시저를 검색 프로시저에서 레이블로 점프 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2628-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="f2628-107">대상으로 지정 하는 레이블과 중복 하는 경우는 `GoTo` 문이 아닌는 `On Error GoTo` 문에서 원하는 대상와 일치 하도록 줄 레이블을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2628-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2628-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2628-108">See also</span></span>

- [<span data-ttu-id="f2628-109">Resume 문</span><span class="sxs-lookup"><span data-stu-id="f2628-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="f2628-110">On Error 문</span><span class="sxs-lookup"><span data-stu-id="f2628-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
