---
title: 개체 변수 할당(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
ms.openlocfilehash: 59dea45511ba8d7d10c95cf17e47981124c532e4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631061"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="a26a4-102">개체 변수 할당(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a26a4-102">Object Variable Assignment (Visual Basic)</span></span>

<span data-ttu-id="a26a4-103">개체를 개체 변수에 할당 하는 데 일반 대입문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="a26a4-104">다음 예제와 같이 개체 식 또는 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>

```vb
Dim thisObject As Object
' The following statement assigns an object reference.
thisObject = Form1
' The following statement discontinues association with any object.
thisObject = Nothing
```

<span data-ttu-id="a26a4-105">`Nothing`현재 변수에 할당 된 개체가 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-105">`Nothing` means there is no object currently assigned to the variable.</span></span>

## <a name="initialization"></a><span data-ttu-id="a26a4-106">초기화</span><span class="sxs-lookup"><span data-stu-id="a26a4-106">Initialization</span></span>

<span data-ttu-id="a26a4-107">코드 실행이 시작 되 면 개체 변수가으로 `Nothing`초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="a26a4-108">선언이 포함 된 선언이 선언 문을 실행할 때 지정 하는 값으로 다시 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>

<span data-ttu-id="a26a4-109">[New](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 사용 하 여 선언에 초기화를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="a26a4-110">다음 선언문은 개체 변수 `testUri` `ver` 를 선언 하 고 여기에 특정 개체를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="a26a4-111">각각은 적절 한 클래스의 오버 로드 된 생성자 중 하나를 사용 하 여 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>

```vb
Dim testUri As New System.Uri("https://www.microsoft.com")
Dim ver As New System.Version(6, 1, 0)
```

## <a name="disassociation"></a><span data-ttu-id="a26a4-112">분리</span><span class="sxs-lookup"><span data-stu-id="a26a4-112">Disassociation</span></span>

<span data-ttu-id="a26a4-113">개체 변수를 설정 하 `Nothing` 여 특정 개체와 변수의 연결을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="a26a4-114">이렇게 하면 변수를 변경 하 여 실수로 개체를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="a26a4-115">또한 다음 예제와 같이 개체 변수가 유효한 개체를 가리키는지 여부를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>

```vb
If otherObject IsNot Nothing Then
    ' otherObject refers to a valid object, so your code can use it.
End If
```

<span data-ttu-id="a26a4-116">변수가 참조 하는 개체가 다른 응용 프로그램에 있는 경우이 테스트는 해당 응용 프로그램이 종료 되었는지 아니면 무효화 되었는지를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>

<span data-ttu-id="a26a4-117">값 `Nothing` 을 포함 하는 개체 변수를 *null 참조*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>

## <a name="current-instance"></a><span data-ttu-id="a26a4-118">현재 인스턴스</span><span class="sxs-lookup"><span data-stu-id="a26a4-118">Current Instance</span></span>

<span data-ttu-id="a26a4-119">개체의 *현재 인스턴스* 는 코드가 현재 실행 중인 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="a26a4-120">모든 코드가 프로시저 내에서 실행 되기 때문에 현재 인스턴스는 프로시저가 호출 된 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>

<span data-ttu-id="a26a4-121">키워드 `Me` 는 현재 인스턴스를 참조 하는 개체 변수의 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="a26a4-122">프로시저를 [공유](../../../../visual-basic/language-reference/modifiers/shared.md)하지 않는 경우 `Me` 키워드를 사용 하 여 현재 인스턴스에 대 한 포인터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="a26a4-123">공유 프로시저는 특정 클래스 인스턴스와 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>

<span data-ttu-id="a26a4-124">는 `Me` 현재 인스턴스를 다른 모듈의 프로시저에 전달 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="a26a4-125">예를 들어 여러 XML 문서를 포함 하 고 모든 표준 텍스트를이 문서에 추가 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="a26a4-126">다음 예에서는이 작업을 수행 하는 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-126">The following example defines a procedure to do this.</span></span>

```vb
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)
    XmlDoc.CreateTextNode("This text goes into every XML document.")
End Sub
```

<span data-ttu-id="a26a4-127">그러면 모든 XML 문서 개체가 프로시저를 호출 하 고 현재 인스턴스를 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="a26a4-128">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a26a4-128">The following example demonstrates this.</span></span>

```vb
addStandardText(Me)
```

## <a name="see-also"></a><span data-ttu-id="a26a4-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="a26a4-129">See also</span></span>

- [<span data-ttu-id="a26a4-130">개체 변수</span><span class="sxs-lookup"><span data-stu-id="a26a4-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="a26a4-131">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="a26a4-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="a26a4-132">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="a26a4-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="a26a4-133">방법: 개체 변수를 선언 하 고 개체를에 할당 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a26a4-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="a26a4-134">방법: 개체 변수가 인스턴스를 참조 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="a26a4-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="a26a4-135">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="a26a4-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
