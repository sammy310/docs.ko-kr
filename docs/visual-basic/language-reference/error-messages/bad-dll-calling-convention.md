---
title: DLL 호출 규칙이 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: a60e44ce92b1805b0a5a6f1d4ce397c295eef202
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409883"
---
# <a name="bad-dll-calling-convention"></a><span data-ttu-id="b9991-102">DLL 호출 규칙이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-102">Bad DLL calling convention</span></span>
<span data-ttu-id="b9991-103">DLL (동적 연결 라이브러리)로 전달 되는 인수는 루틴에서 예상한 것과 정확히 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-103">Arguments passed to a dynamic-link library (DLL) must exactly match those expected by the routine.</span></span> <span data-ttu-id="b9991-104">호출 규칙은 인수의 개수, 형식 및 순서를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-104">Calling conventions deal with number, type, and order of arguments.</span></span> <span data-ttu-id="b9991-105">프로그램에서 잘못 된 형식이 나 인수 개수가 전달 되는 DLL의 루틴을 호출 하 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-105">Your program may be calling a routine in a DLL that is being passed the wrong type or number of arguments.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b9991-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b9991-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b9991-107">모든 인수 형식이 호출 하는 루틴의 선언에 지정 된 것과 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-107">Make sure all argument types agree with those specified in the declaration of the routine that you are calling.</span></span>  
  
2. <span data-ttu-id="b9991-108">호출 하는 루틴의 선언에 표시 된 것과 동일한 수의 인수를 전달 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-108">Make sure you are passing the same number of arguments indicated in the declaration of the routine that you are calling.</span></span>  
  
3. <span data-ttu-id="b9991-109">DLL 루틴에 값으로 인수가 필요한 경우 `ByVal` 루틴 선언에서 해당 인수에 대해가 지정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9991-109">If the DLL routine expects arguments by value, make sure `ByVal` is specified for those arguments in the declaration for the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9991-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9991-110">See also</span></span>

- [<span data-ttu-id="b9991-111">오류 유형</span><span class="sxs-lookup"><span data-stu-id="b9991-111">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="b9991-112">Call 문</span><span class="sxs-lookup"><span data-stu-id="b9991-112">Call Statement</span></span>](../statements/call-statement.md)
- [<span data-ttu-id="b9991-113">Declare 문</span><span class="sxs-lookup"><span data-stu-id="b9991-113">Declare Statement</span></span>](../statements/declare-statement.md)
