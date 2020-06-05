---
title: "'<variablename>' 변수는 바깥쪽 블록에 있는 변수를 숨깁니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406523"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="77461-102">'\<variablename>' 변수는 바깥쪽 블록에 있는 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="77461-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="77461-103">블록에 포함 된 변수는 다른 지역 변수와 동일한 이름을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="77461-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="77461-104">**오류 ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="77461-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77461-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="77461-105">To correct this error</span></span>  
  
- <span data-ttu-id="77461-106">다른 지역 변수와 동일 하지 않도록 포함 된 블록의 변수 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77461-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="77461-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77461-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="77461-108">이 오류의 일반적인 원인은 이벤트 처리기 내에서를 사용 하는 것입니다 `Catch e As Exception` .</span><span class="sxs-lookup"><span data-stu-id="77461-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="77461-109">이 경우에는 `Catch` 대신 블록 변수의 이름을로 `ex` `e` 합니다.</span><span class="sxs-lookup"><span data-stu-id="77461-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="77461-110">이 오류의 또 다른 일반적인 소스는 블록 내에서 선언 된 지역 변수를 별도의 블록에 액세스 하려고 시도 하는 것입니다 `Try` `Catch` .</span><span class="sxs-lookup"><span data-stu-id="77461-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="77461-111">이를 해결 하려면 구조체 외부에서 변수를 선언 합니다 `Try...Catch...Finally` .</span><span class="sxs-lookup"><span data-stu-id="77461-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77461-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77461-112">See also</span></span>

- [<span data-ttu-id="77461-113">Try...Catch...Finally 명령문</span><span class="sxs-lookup"><span data-stu-id="77461-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="77461-114">변수 선언</span><span class="sxs-lookup"><span data-stu-id="77461-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
