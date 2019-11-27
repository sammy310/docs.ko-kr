---
title: '방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 83670ae6af0904156b08398024658cf504b7663f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346825"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="51203-102">방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51203-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="51203-103">여러 메서드 및 속성의 정규화 경로를 필요로 하는 개체에 자주 액세스 하는 경우 한정 경로를 반복 하지 않고 코드 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51203-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="51203-104">두 가지 방법으로 한정 경로를 반복 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51203-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="51203-105">개체를 변수에 할당 하거나 `With`...`End With` 블록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51203-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="51203-106">변수에 할당 하 여 높은 정규화 된 개체에 대 한 액세스 속도를 높이려면</span><span class="sxs-lookup"><span data-stu-id="51203-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="51203-107">자주 액세스 하는 개체의 형식에 대 한 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="51203-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="51203-108">선언의 초기화 부분에서 한정 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="51203-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="51203-109">변수를 사용 하 여 개체의 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="51203-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="51203-110">을 사용 하 여 높은 정규화 된 개체에 대 한 액세스 속도를 높이려면 ... 블록으로 끝</span><span class="sxs-lookup"><span data-stu-id="51203-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="51203-111">`With` 문에 한정 경로를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="51203-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="51203-112">`End With` 문 앞에 `With` 블록 내에서 개체의 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="51203-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="51203-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51203-113">See also</span></span>

- [<span data-ttu-id="51203-114">개체 변수</span><span class="sxs-lookup"><span data-stu-id="51203-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="51203-115">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="51203-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
