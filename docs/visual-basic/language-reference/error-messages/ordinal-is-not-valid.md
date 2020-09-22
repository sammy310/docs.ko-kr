---
title: 서수가 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871387"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="9fa34-102">서수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-102">Ordinal is not valid</span></span>

<span data-ttu-id="9fa34-103">구문을 사용 하 여 프로시저 이름 대신 숫자를 사용 하는 것으로 표시 된 DLL (동적 연결 라이브러리)에 대 한 호출 `#num` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="9fa34-104">이 오류는 다음과 같은 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="9fa34-105">`#num`식을 서 수로 변환 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="9fa34-106">`#num`지정 된가 DLL에서 함수를 지정 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="9fa34-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="9fa34-107">형식 라이브러리의 선언이 잘못 되어 잘못 된 서 수를 내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9fa34-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9fa34-108">To correct this error</span></span>  
  
1. <span data-ttu-id="9fa34-109">식이 유효한 숫자를 나타내는지 확인 하거나 이름을 기준으로 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="9fa34-110">`#num`DLL에서 올바른 함수를 식별 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="9fa34-111">코드를 주석으로 처리 하 여 문제를 일으킨 프로시저 호출을 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="9fa34-112">`Declare`프로시저에 대 한 문을 작성 하 고 형식 라이브러리 공급 업체에 문제를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fa34-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fa34-113">참조</span><span class="sxs-lookup"><span data-stu-id="9fa34-113">See also</span></span>

- [<span data-ttu-id="9fa34-114">Declare 문</span><span class="sxs-lookup"><span data-stu-id="9fa34-114">Declare Statement</span></span>](../statements/declare-statement.md)
