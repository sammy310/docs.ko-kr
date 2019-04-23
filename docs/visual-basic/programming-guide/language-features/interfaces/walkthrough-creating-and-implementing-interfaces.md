---
title: 인터페이스 (Visual Basic) 만들기 및 구현
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
ms.openlocfilehash: faed4d3c9498938e022daf821dd0aefbcbcf2e8d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322032"
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="3a15b-102">연습: 인터페이스 (Visual Basic) 만들기 및 구현</span><span class="sxs-lookup"><span data-stu-id="3a15b-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>

<span data-ttu-id="3a15b-103">인터페이스는 속성, 메서드 및 이벤트의 특징을 설명 하지만 구조체 또는 클래스까지 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="3a15b-104">이 연습에는 선언 및 인터페이스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a15b-105">이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-an-interface"></a><span data-ttu-id="3a15b-106">인터페이스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="3a15b-106">To define an interface</span></span>
  
1. <span data-ttu-id="3a15b-107">새 Visual Basic Windows 애플리케이션 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-107">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="3a15b-108">새 모듈을 클릭 하 여 프로젝트에 추가할 **모듈 추가** 에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="3a15b-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3. <span data-ttu-id="3a15b-109">새 모듈의 이름을 `Module1.vb` 누릅니다 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="3a15b-110">새 모듈의 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-110">The code for the new module is displayed.</span></span>  
  
4. <span data-ttu-id="3a15b-111">라는 인터페이스를 정의 `TestInterface` 내에서 `Module1` 입력 하 여 `Interface TestInterface` 간에 `Module` 및 `End Module` 문 및 ENTER 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="3a15b-112">합니다 **코드 편집기** 들여쓰기를 `Interface` 키워드 추가 `End Interface` 코드 블록을 형성 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5. <span data-ttu-id="3a15b-113">속성, 메서드 및 인터페이스에 대 한 이벤트 사이 다음 코드를 배치 하 여 정의 된 `Interface` 및 `End Interface` 문:</span><span class="sxs-lookup"><span data-stu-id="3a15b-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#98)]
  
## <a name="implementation"></a><span data-ttu-id="3a15b-114">구현</span><span class="sxs-lookup"><span data-stu-id="3a15b-114">Implementation</span></span>

 <span data-ttu-id="3a15b-115">인터페이스 멤버를 선언 하는 데 구문이 클래스 멤버를 선언 하는 데 사용 되는 구문에서 다른 지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="3a15b-116">이러한 차이 인터페이스 구현 코드를 포함할 수 없습니다 사실을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
### <a name="to-implement-the-interface"></a><span data-ttu-id="3a15b-117">인터페이스를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="3a15b-117">To implement the interface</span></span>
  
1. <span data-ttu-id="3a15b-118">라는 클래스를 추가 `ImplementationClass` 다음 문을 추가 하 여 `Module1`뒤를 `End Interface` 문의 하기 전에 `End Module` 문 및 enter 키를 눌러:</span><span class="sxs-lookup"><span data-stu-id="3a15b-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#99)]
  
     <span data-ttu-id="3a15b-119">통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 일치 하는 제공 `End Class` ENTER 키를 누르면 문입니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2. <span data-ttu-id="3a15b-120">다음을 추가 합니다 `Implements` 문을 `ImplementationClass`를 구현 하는 인터페이스 클래스의 이름을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#100)]
  
     <span data-ttu-id="3a15b-121">클래스 또는 구조체의 맨 위에 있는 다른 항목과 별도로 나열 하는 경우는 `Implements` 문을 클래스 또는 구조체는 인터페이스를 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="3a15b-122">통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 구현에 필요한 클래스 멤버 `TestInterface` 경우 ENTER 키를 누릅니다 하 고 다음 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3. <span data-ttu-id="3a15b-123">인터페이스의 모든 멤버를 구현 해야 통합된 개발 환경 내에서 작동 하지 않는 경우 `MyInterface`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="3a15b-124">다음 코드를 추가 `ImplementationClass` 구현 `Event1`를 `Method1`, 및 `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="3a15b-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#101)]
  
     <span data-ttu-id="3a15b-125">`Implements` 문을 인터페이스 및 인터페이스 구현 되는 멤버 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4. <span data-ttu-id="3a15b-126">정의 완료 `Prop1` 속성 값을 저장 하는 클래스에는 개인 필드를 추가 하 여:</span><span class="sxs-lookup"><span data-stu-id="3a15b-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#102)]
  
     <span data-ttu-id="3a15b-127">값을 반환 합니다 `pval` 속성에서 접근자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#103)]
  
     <span data-ttu-id="3a15b-128">값을 설정할 `pval` 속성에 set 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#104)]
  
5. <span data-ttu-id="3a15b-129">정의 완료 `Method1` 다음 코드를 추가 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#105)]
  
### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="3a15b-130">인터페이스의 구현을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="3a15b-130">To test the implementation of the interface</span></span>
  
1. <span data-ttu-id="3a15b-131">프로젝트의 시작 폼을 마우스 오른쪽 단추로 클릭 합니다 **솔루션 탐색기**, 클릭 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="3a15b-132">편집기 시작 폼에 대 한 클래스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="3a15b-133">기본적으로 시작 폼 이라고 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-133">By default, the startup form is called `Form1`.</span></span>  
  
2. <span data-ttu-id="3a15b-134">다음을 추가 합니다 `testInstance` 필드는 `Form1` 클래스:</span><span class="sxs-lookup"><span data-stu-id="3a15b-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#120)]
  
     <span data-ttu-id="3a15b-135">선언 하 여 `testInstance` 으로 `WithEvents`, `Form1` 클래스는 해당 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3. <span data-ttu-id="3a15b-136">다음 이벤트 처리기를 추가 합니다 `Form1` 클래스에 의해 발생 하는 이벤트를 처리할 `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="3a15b-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#106)]
  
4. <span data-ttu-id="3a15b-137">라는 이름의 서브루틴을 추가 `Test` 에 `Form1` 클래스 구현 클래스를 테스트 하려면:</span><span class="sxs-lookup"><span data-stu-id="3a15b-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#107)]
  
     <span data-ttu-id="3a15b-138">`Test` 프로시저를 구현 하는 클래스의 인스턴스를 만듭니다 `MyInterface`, 해당 인스턴스를 할당 합니다 `testInstance` 필드 속성을 설정 하 고 인터페이스를 통해 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5. <span data-ttu-id="3a15b-139">호출 하는 코드를 추가 합니다 `Test` 프로시저를 `Form1 Load` 시작 폼의 프로시저:</span><span class="sxs-lookup"><span data-stu-id="3a15b-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#108)]
  
6. <span data-ttu-id="3a15b-140">실행 된 `Test` f5 키를 눌러 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="3a15b-141">메시지 "Prop1 설정한 9" 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="3a15b-142">클릭 한 후, 메시지 "Method1에 대 한 X 매개 변수는 5입니다"가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="3a15b-143">확인을 클릭 하 고 "이벤트 처리기는 이벤트를 포착 하는 데 사용" 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a15b-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a15b-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="3a15b-144">See also</span></span>

- [<span data-ttu-id="3a15b-145">Implements 문</span><span class="sxs-lookup"><span data-stu-id="3a15b-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="3a15b-146">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a15b-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [<span data-ttu-id="3a15b-147">Interface 문</span><span class="sxs-lookup"><span data-stu-id="3a15b-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="3a15b-148">Event 문</span><span class="sxs-lookup"><span data-stu-id="3a15b-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
