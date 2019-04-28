---
title: "'<variablename>' 변수는 바깥쪽 블록에 있는 변수를 숨깁니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 15c35cbb829bec782771b584ea25b111b81b5e1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766892"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="916be-102">변수 '\<variablename >'가 바깥쪽 블록의 변수를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="916be-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>
<span data-ttu-id="916be-103">블록에 포함 된 변수의 다른 로컬 변수와 동일한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="916be-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="916be-104">**오류 ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="916be-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="916be-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="916be-105">To correct this error</span></span>  
  
- <span data-ttu-id="916be-106">블록 내부에서 변수를 이름을 다른 지역 변수와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="916be-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="916be-107">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="916be-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="916be-108">이 오류는 일반적으로 사용 하는 것 `Catch e As Exception` 이벤트 처리기의 내부.</span><span class="sxs-lookup"><span data-stu-id="916be-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="916be-109">이 경우 이름을 합니다 `Catch` 블록 변수가 `ex` 대신 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="916be-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="916be-110">이 오류는 또 다른 일반적인 소스 내에 선언 된 지역 변수에 액세스 하려고 하는 한 `Try` 별도의 차단 `Catch` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="916be-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="916be-111">이 해결 하려면 외부에서 변수를 선언 합니다 `Try...Catch...Finally` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="916be-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916be-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="916be-112">See also</span></span>

- [<span data-ttu-id="916be-113">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="916be-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="916be-114">변수 선언</span><span class="sxs-lookup"><span data-stu-id="916be-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
