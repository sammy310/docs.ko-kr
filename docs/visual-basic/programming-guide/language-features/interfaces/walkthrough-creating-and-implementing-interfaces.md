---
title: 인터페이스 만들기 및 구현
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: 47176d2e7a512d8e8c27a90ac04d2a2a2af274b5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345036"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="3e233-102">연습: 인터페이스 만들기 및 구현(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e233-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="3e233-103">인터페이스는 속성, 메서드 및 이벤트의 특성을 설명 하지만, 구현 세부 정보는 구조체 또는 클래스까지 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="3e233-104">이 연습에서는 인터페이스를 선언 하 고 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3e233-105">이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="3e233-106">인터페이스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="3e233-106">To define an interface</span></span>
  
1. <span data-ttu-id="3e233-107">새 Visual Basic Windows 애플리케이션 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="3e233-108">**프로젝트** 메뉴에서 **모듈 추가** 를 클릭 하 여 프로젝트에 새 모듈을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="3e233-109">새 모듈의 이름을 `Module1.vb` 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="3e233-110">새 모듈의 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="3e233-111">`Module`와 `End Module` 문 사이에 `Interface TestInterface`를 입력 하 고 ENTER 키를 눌러 `Module1` 내에서 `TestInterface` 이라는 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="3e233-112">**코드 편집기** 는 `Interface` 키워드를 들여쓰 며 `End Interface` 문을 추가 하 여 코드 블록을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="3e233-113">`Interface` 문과 `End Interface` 문 사이에 다음 코드를 배치 하 여 인터페이스에 대 한 속성, 메서드 및 이벤트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="3e233-114">구현</span><span class="sxs-lookup"><span data-stu-id="3e233-114">Implementation</span></span>

 <span data-ttu-id="3e233-115">인터페이스 멤버를 선언 하는 데 사용 되는 구문은 클래스 멤버를 선언 하는 데 사용 되는 구문과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="3e233-116">이러한 차이는 인터페이스에 구현 코드가 포함 될 수 없다는 사실을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="3e233-117">인터페이스를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="3e233-117">To implement the interface</span></span>
  
1. <span data-ttu-id="3e233-118">다음 문을 추가 하 여 `ImplementationClass` 라는 클래스를 추가 하 고 `End Interface` 문 뒤에 `End Module` 문 앞에 `Module1`한 다음 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="3e233-119">통합 개발 환경 내에서 작업 하는 경우 ENTER 키를 누르면 **코드 편집기** 에서 일치 하는 `End Class` 문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="3e233-120">클래스가 구현 하는 인터페이스의 이름을 `ImplementationClass`에 다음 `Implements` 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="3e233-121">클래스 또는 구조체의 맨 위에 있는 다른 항목과 별도로 나열 될 경우 `Implements` 문은 클래스 또는 구조체가 인터페이스를 구현 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="3e233-122">통합 개발 환경 내에서 작업 하는 경우 **코드 편집기** 는 enter 키를 누를 때 `TestInterface`에 필요한 클래스 멤버를 구현 하 고 다음 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="3e233-123">통합 개발 환경 내에서 작업 하지 않는 경우 `MyInterface`인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="3e233-124">`ImplementationClass`에 다음 코드를 추가 하 여 `Event1`, `Method1`및 `Prop1`을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="3e233-125">`Implements` 문은 구현할 인터페이스와 인터페이스 멤버의 이름을로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="3e233-126">속성 값을 저장 한 클래스에 전용 필드를 추가 하 여 `Prop1`의 정의를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="3e233-127">속성 get 접근자에서 `pval` 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="3e233-128">속성 집합 접근자에서 `pval` 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="3e233-129">다음 코드를 추가 하 여 `Method1`의 정의를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="3e233-130">인터페이스 구현을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="3e233-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="3e233-131">**솔루션 탐색기**에서 프로젝트의 시작 폼을 마우스 오른쪽 단추로 클릭 하 고 **코드 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="3e233-132">편집기에서 시작 폼의 클래스를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="3e233-133">기본적으로 시작 폼을 `Form1`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="3e233-134">`Form1` 클래스에 다음 `testInstance` 필드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="3e233-135">`testInstance`를 `WithEvents`로 선언 하면 `Form1` 클래스가 해당 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="3e233-136">`Form1` 클래스에 다음 이벤트 처리기를 추가 하 여 `testInstance`에서 발생 한 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="3e233-137">`Test` 라는 서브루틴을 `Form1` 클래스에 추가 하 여 구현 클래스를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="3e233-138">`Test` 프로시저는 `MyInterface`를 구현 하는 클래스의 인스턴스를 만들고, 해당 인스턴스를 `testInstance` 필드에 할당 하 고, 속성을 설정 하 고, 인터페이스를 통해 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="3e233-139">시작 폼의 `Form1 Load` 프로시저에서 `Test` 프로시저를 호출 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="3e233-140">F5 키를 눌러 `Test` 프로시저를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="3e233-141">"Prop1가 9로 설정 되었습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="3e233-142">확인을 클릭 하면 "Method1의 X 매개 변수가 5입니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="3e233-143">확인을 클릭 하면 "이벤트를 catch 했습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e233-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e233-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e233-144">See also</span></span>

- [<span data-ttu-id="3e233-145">Implements 문</span><span class="sxs-lookup"><span data-stu-id="3e233-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="3e233-146">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e233-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="3e233-147">Interface 문</span><span class="sxs-lookup"><span data-stu-id="3e233-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="3e233-148">Event 문</span><span class="sxs-lookup"><span data-stu-id="3e233-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
