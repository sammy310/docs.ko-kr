---
title: '방법: 정규화 경로가 긴 (Visual Basic)를 사용 하 여 개체에 대 한 액세스 속도'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 94c838a69aab9fcae9dc0c79b6038ee90e2369e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769046"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="91385-102">방법: 정규화 경로가 긴 (Visual Basic)를 사용 하 여 개체에 대 한 액세스 속도</span><span class="sxs-lookup"><span data-stu-id="91385-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="91385-103">여러 메서드 및 속성을 정규화 된 경로 필요로 하는 개체에 자주 액세스 하지는 정규화 된 경로 반복 하 여 코드 속도 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91385-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="91385-104">두 가지 방법으로 정규화 된 경로 반복을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91385-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="91385-105">개체를 변수에 할당할 수 있습니다 또는 사용할 수는 `With`... `End With` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="91385-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="91385-106">변수에 할당 하 여 과도 하 게 정규화 된 개체에 대 한 액세스 속도</span><span class="sxs-lookup"><span data-stu-id="91385-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1. <span data-ttu-id="91385-107">자주 액세스 하는 개체 유형의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="91385-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="91385-108">선언의 초기화 부분에는 정규화 된 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91385-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2. <span data-ttu-id="91385-109">개체의 멤버에 액세스 하는 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="91385-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="91385-110">With를 사용 하 여 액세스를 과도 하 게 정규화 된 개체를 가속화 하는 중... End 블록</span><span class="sxs-lookup"><span data-stu-id="91385-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1. <span data-ttu-id="91385-111">정규화 된 경로에 배치 된 `With` 문.</span><span class="sxs-lookup"><span data-stu-id="91385-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2. <span data-ttu-id="91385-112">내에서 개체의 멤버에 액세스 합니다 `With` 차단 하기 전에 `End With` 문.</span><span class="sxs-lookup"><span data-stu-id="91385-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="91385-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="91385-113">See also</span></span>

- [<span data-ttu-id="91385-114">개체 변수</span><span class="sxs-lookup"><span data-stu-id="91385-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="91385-115">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="91385-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
