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
ms.openlocfilehash: dff1b9bb9e87f827663786cac3f33531db41b2c1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757068"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="cdc7d-102">개체 변수 할당(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdc7d-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="cdc7d-103">일반적인 대입문을를 사용 하 여 개체를 개체 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="cdc7d-104">개체 식을 할당할 수 있습니다 또는 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드, 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="cdc7d-105">`Nothing` 즉, 변수에 현재 할당 된 개체가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="cdc7d-106">초기화</span><span class="sxs-lookup"><span data-stu-id="cdc7d-106">Initialization</span></span>  
 <span data-ttu-id="cdc7d-107">코드를 실행 하 고 변수가 초기화 됩니다 개체 시작 될 때 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="cdc7d-108">초기화를 포함 하는 해당 선언 된 선언 문이 실행 될 때 지정 된 값을 다시 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="cdc7d-109">사용 하 여 선언에서 초기화를 포함할 수는 [새로 만들기](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="cdc7d-110">개체 변수를 선언 하는 다음 선언문 `testUri` 고 `ver` 을 특정 개체를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="cdc7d-111">각 사용 하 여 해당 클래스의 오버 로드 된 생성자 중 하나 개체를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="cdc7d-112">연결 해제</span><span class="sxs-lookup"><span data-stu-id="cdc7d-112">Disassociation</span></span>  
 <span data-ttu-id="cdc7d-113">개체 변수 설정 `Nothing` 변수의 특정 개체를 사용 하 여 연결을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="cdc7d-114">이렇게 하면 실수로 변수를 변경 하 여 개체를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="cdc7d-115">개체 변수를 다음 예제와 같이 유효한 개체를 가리키는 여부를 테스트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="cdc7d-116">변수를 나타내는 개체를 다른 응용 프로그램의 경우이 테스트는 해당 응용 프로그램 종료 했거나 방금 개체를 무효화 하는지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="cdc7d-117">개체 변수 값을 사용 하 여 `Nothing` 라고도 함은 *null 참조*합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="cdc7d-118">현재 인스턴스</span><span class="sxs-lookup"><span data-stu-id="cdc7d-118">Current Instance</span></span>  
 <span data-ttu-id="cdc7d-119">*현재 인스턴스* 개체는 코드가 현재 실행 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="cdc7d-120">모든 코드가 프로시저 내에서 실행 되므로 현재 인스턴스가 프로시저가 호출 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="cdc7d-121">`Me` 키워드는 현재 인스턴스를 참조 하는 개체 변수로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="cdc7d-122">프로시저 없으면 [공유](../../../../visual-basic/language-reference/modifiers/shared.md)를 사용할 수 있습니다를 `Me` 키워드를 현재 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="cdc7d-123">공유 프로시저 클래스의 특정 인스턴스와 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="cdc7d-124">사용 하 여 `Me` 프로시저 다른 모듈에 현재 인스턴스를 전달 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="cdc7d-125">예를 들어, XML 문서 수가 하 고 이들 모두에 표준 텍스트를 추가.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="cdc7d-126">다음 예제에서는이 작업을 수행 하는 절차를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="cdc7d-127">그런 다음 모든 XML 문서 개체는 프로시저를 호출 하 고 현재 인스턴스를 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="cdc7d-128">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc7d-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc7d-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="cdc7d-129">See also</span></span>

- [<span data-ttu-id="cdc7d-130">개체 변수</span><span class="sxs-lookup"><span data-stu-id="cdc7d-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="cdc7d-131">개체 변수 선언</span><span class="sxs-lookup"><span data-stu-id="cdc7d-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="cdc7d-132">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="cdc7d-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="cdc7d-133">방법: 개체 변수를 선언 하 고 Visual Basic의 개체를 할당</span><span class="sxs-lookup"><span data-stu-id="cdc7d-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)
- [<span data-ttu-id="cdc7d-134">방법: 변수 개체를 만듭니다. 모든 인스턴스를 참조 하지</span><span class="sxs-lookup"><span data-stu-id="cdc7d-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)
- [<span data-ttu-id="cdc7d-135">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="cdc7d-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
