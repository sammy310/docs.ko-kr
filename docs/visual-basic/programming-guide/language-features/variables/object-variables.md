---
title: Visual Basic의 개체 변수
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: cc5be13293a89e73d1790e94a99d7936f1711e12
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352973"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="6c77c-102">Visual Basic의 개체 변수</span><span class="sxs-lookup"><span data-stu-id="6c77c-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="6c77c-103">값에 직접 저장 하는 것 외에도 변수 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="6c77c-104">변수에 값을 변수에 할당할 같은 이유로 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="6c77c-105">변수 이름은 메서드 및 개체 자체에 액세스 하는 데 필요한 속성의 전체 경로 비해 기억 하기 쉽고 자주입니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="6c77c-106">개체를 참조 하는 변수를 사용 하 여 필요한 메서드 또는 속성을 통해 개체 자체를 반복적으로 액세스할 때 보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="6c77c-107">코드를 실행 하는 동안 다른 개체를 참조 하는 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="6c77c-108">짧은 코드</span><span class="sxs-lookup"><span data-stu-id="6c77c-108">Making Code Shorter</span></span>

<span data-ttu-id="6c77c-109">입력 해야 하는 코드를 줄이기 위해 개체 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="6c77c-110">다음 예제에서는 메서드 및 속성의 전체 경로 사용 하 여 액세스 하는 <xref:System.Windows.Forms.Control> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="6c77c-111">이 코드를 줄이고 실행 속도 컨트롤에 대 한 개체 변수를 사용 하는 경우 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="6c77c-112">할당 하려는 특정 클래스를 사용 하 여 개체 변수를 선언 해야 합니다 (`Control` 이 경우).</span><span class="sxs-lookup"><span data-stu-id="6c77c-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="6c77c-113">개체 변수에 할당 하면 처리할 수 있습니다 정확 하 게 동일한 참조 하는 개체를 처리 하는 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="6c77c-114">설정 하 고 또는 개체의 속성을 검색 하 하거나, 해당 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="6c77c-115">다음 예제에서는 앞의 예제에서 코드를 간소화 하는 개체 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c77c-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="6c77c-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c77c-116">See also</span></span>

- [<span data-ttu-id="6c77c-117">변수 선언</span><span class="sxs-lookup"><span data-stu-id="6c77c-117">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="6c77c-118">방법: 정규화 경로가 긴를 사용 하 여 개체에 대 한 액세스 속도</span><span class="sxs-lookup"><span data-stu-id="6c77c-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="6c77c-119">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="6c77c-119">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="6c77c-120">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="6c77c-120">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="6c77c-121">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="6c77c-121">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
