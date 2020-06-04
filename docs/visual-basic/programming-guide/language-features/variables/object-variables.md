---
title: 개체 변수
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: a5e61f9308d3484dc228a7d09cc2fd30a2f41b35
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410337"
---
# <a name="object-variables-in-visual-basic"></a><span data-ttu-id="052b8-102">Visual Basic의 개체 변수</span><span class="sxs-lookup"><span data-stu-id="052b8-102">Object Variables in Visual Basic</span></span>

<span data-ttu-id="052b8-103">변수는 직접 값을 저장 하는 것 외에도 개체를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-103">In addition to storing values directly, a variable can refer to an object.</span></span> <span data-ttu-id="052b8-104">변수에 값을 할당 하는 것과 같은 이유로 개체를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-104">You assign an object to a variable for the same reasons you assign any value to a variable:</span></span>

- <span data-ttu-id="052b8-105">변수 이름은 개체 자체에 액세스 하는 데 필요한 메서드 및 속성의 전체 경로 보다 짧고 쉽게 기억할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-105">A variable name is often shorter and easier to remember than the full path of methods and properties necessary to access the object itself.</span></span>

- <span data-ttu-id="052b8-106">개체를 참조 하는 변수를 사용 하는 것은 필요한 메서드나 속성을 통해 개체 자체에 반복 해 서 액세스 하는 것 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-106">Using a variable that refers to an object is more efficient than repeatedly accessing the object itself through the necessary methods or properties.</span></span>

- <span data-ttu-id="052b8-107">코드를 실행 하는 동안 다른 개체를 참조 하도록 변수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-107">You can change a variable to refer to other objects while your code is running.</span></span>

## <a name="making-code-shorter"></a><span data-ttu-id="052b8-108">코드 더 짧게 만들기</span><span class="sxs-lookup"><span data-stu-id="052b8-108">Making Code Shorter</span></span>

<span data-ttu-id="052b8-109">개체 변수를 사용 하 여 입력 해야 하는 코드를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-109">You can use object variables to shorten the code you have to type.</span></span> <span data-ttu-id="052b8-110">다음 예제에서는 메서드 및 속성의 전체 경로를 사용 하 여 개체에 액세스 <xref:System.Windows.Forms.Control> 합니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-110">The following example uses the full path of methods and properties to access a <xref:System.Windows.Forms.Control> object.</span></span>

```vb
' Assume Me is a valid Form, or replace Me with a valid Form.
Me.ActiveForm.ActiveControl.Text = "Test"
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)
Me.ActiveForm.ActiveControl.Show()
```

<span data-ttu-id="052b8-111">컨트롤에 개체 변수를 사용 하는 경우이 코드를 줄이고 실행 속도를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-111">You can shorten this code, and speed up execution, if you use an object variable for the control.</span></span> <span data-ttu-id="052b8-112">할당 하려는 특정 클래스 (이 경우)를 사용 하 여 개체 변수를 선언 해야 합니다 `Control` .</span><span class="sxs-lookup"><span data-stu-id="052b8-112">You should declare the object variable with the specific class that you intend to assign to it (`Control` in this case).</span></span> <span data-ttu-id="052b8-113">개체를 변수에 할당 한 후에는 개체를 참조 하는 개체를 처리 하는 것과 동일 하 게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-113">Once you assign an object to the variable, you can treat it exactly the same as you treat the object to which it refers.</span></span> <span data-ttu-id="052b8-114">개체의 속성을 설정 또는 검색 하거나 해당 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-114">You can set or retrieve the properties of the object or use any of its methods.</span></span> <span data-ttu-id="052b8-115">다음 예제에서는 개체 변수를 사용 하 여 앞의 예제에서 코드를 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="052b8-115">The following example uses an object variable to simplify the code in the preceding example.</span></span>

```vb
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl
ctrlActv.Text = "Test"
ctrlActv.Location = New Point(100, 100)
ctrlActv.Show()
```

## <a name="see-also"></a><span data-ttu-id="052b8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="052b8-116">See also</span></span>

- [<span data-ttu-id="052b8-117">변수 선언</span><span class="sxs-lookup"><span data-stu-id="052b8-117">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="052b8-118">방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선</span><span class="sxs-lookup"><span data-stu-id="052b8-118">How to: Speed Up Access to an Object with a Long Qualification Path</span></span>](how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [<span data-ttu-id="052b8-119">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="052b8-119">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="052b8-120">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="052b8-120">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="052b8-121">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="052b8-121">Object Variable Values</span></span>](object-variable-values.md)
