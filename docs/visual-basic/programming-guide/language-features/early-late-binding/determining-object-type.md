---
title: 개체 형식 확인(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 4014bef2e0c27a0f6a684bc1ed95019f392062a5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59302714"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="04ff7-102">개체 형식 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04ff7-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="04ff7-103">일반 개체 변수 (즉, 변수 선언으로 `Object`) 모든 클래스의 개체를에서 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="04ff7-104">형식의 변수를 사용 하는 경우 `Object`, 개체의 클래스를 기반으로 하는 다른 작업을 수행 해야; 예를 들어, 일부 개체 수 지원 하지는 특정 속성 또는 메서드.</span><span class="sxs-lookup"><span data-stu-id="04ff7-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="04ff7-105">Visual Basic에서 어떤 유형의 개체를 개체 변수에 저장 됨을 결정 하는 두 가지 방법을 제공 합니다:는 `TypeName` 함수 및 `TypeOf...Is` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="04ff7-106">TypeName 및 TypeOf... 는</span><span class="sxs-lookup"><span data-stu-id="04ff7-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="04ff7-107">`TypeName` 함수 문자열을 반환 하며 다음 코드 조각에 나와 있는 것 처럼 개체의 클래스 이름을 저장 하거나 표시 해야 할 때 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="04ff7-108">합니다 `TypeOf...Is` 연산자는 개체의 형식을 테스트에 가장 적합 한 사용 하 여 해당 하는 문자열 비교 보다 훨씬 빠릅니다 `TypeName`합니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="04ff7-109">다음 코드 조각을 사용 하 여 `TypeOf...Is` 내는 `If...Then...Else` 문:</span><span class="sxs-lookup"><span data-stu-id="04ff7-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="04ff7-110">주의할 여기 기한입니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-110">A word of caution is due here.</span></span> <span data-ttu-id="04ff7-111">`TypeOf...Is` 연산자는 반환 `True` 개체는 특정 유형의 되었거나 특정 형식에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="04ff7-112">Visual Basic을 사용 하 여 수행 하는 거의 모든 문자열 및 정수 등의 개체로 생각할 일반적으로 일부 요소를 포함 하는 개체에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="04ff7-113">이러한 개체에서 파생 되 고 메서드를 상속 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="04ff7-114">전달 하는 경우는 `Integer` 사용 하 여 평가 하 고 `Object`의 `TypeOf...Is` 연산자를 반환 합니다 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="04ff7-115">다음 예제를 보고 하는 매개 변수 `InParam` 이기는 `Object` 및 `Integer`:</span><span class="sxs-lookup"><span data-stu-id="04ff7-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="04ff7-116">다음 예제에서는 둘 다 `TypeOf...Is` 및 `TypeName` 전달 하는 개체의 형식을 결정 하는 `Ctrl` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="04ff7-117">합니다 `TestObject` 프로시저 호출 `ShowType` 서로 다른 세 가지 컨트롤을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="04ff7-118">예제를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="04ff7-118">To run the example</span></span>  
  
1. <span data-ttu-id="04ff7-119">새 Windows 응용 프로그램 프로젝트를 만들고 추가 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.CheckBox> 컨트롤 및 <xref:System.Windows.Forms.RadioButton> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="04ff7-120">폼에 단추에서 호출 된 `TestObject` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="04ff7-121">폼에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="04ff7-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="04ff7-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="04ff7-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="04ff7-123">문자열 이름을 사용하여 속성 또는 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="04ff7-123">Calling a Property or Method Using a String Name</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="04ff7-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="04ff7-124">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="04ff7-125">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="04ff7-125">If...Then...Else Statement</span></span>](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="04ff7-126">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04ff7-126">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="04ff7-127">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="04ff7-127">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)
