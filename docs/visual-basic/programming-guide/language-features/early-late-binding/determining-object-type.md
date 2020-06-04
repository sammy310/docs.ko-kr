---
title: 개체 형식 확인
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], discovering which an object belongs to
- types [Visual Basic], determining Visual Basic object types
- object variables [Visual Basic], testing values
- TypeOf...Is expression, object type at run time
- TypeName function
- objects [Visual Basic], type determining
ms.assetid: d95e7ad1-cd63-41d6-9a28-d7a1380d49c1
ms.openlocfilehash: 3b1c4ad0ab4fd8d2897aff6ad9097cdc81272455
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410646"
---
# <a name="determining-object-type-visual-basic"></a><span data-ttu-id="5a589-102">개체 형식 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a589-102">Determining Object Type (Visual Basic)</span></span>
<span data-ttu-id="5a589-103">제네릭 개체 변수 (즉,로 선언 하는 변수 `Object` )는 모든 클래스의 개체를 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-103">Generic object variables (that is, variables you declare as `Object`) can hold objects from any class.</span></span> <span data-ttu-id="5a589-104">형식의 변수를 사용 하는 경우 `Object` 개체의 클래스에 따라 다른 작업을 수행 해야 할 수 있습니다. 예를 들어 일부 개체는 특정 속성이 나 메서드를 지원 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-104">When using variables of type `Object`, you may need to take different actions based on the class of the object; for example, some objects might not support a particular property or method.</span></span> <span data-ttu-id="5a589-105">Visual Basic은 개체 변수에 저장 되는 개체의 형식, 함수 및 연산자를 결정 하는 두 가지 방법을 제공 `TypeName` `TypeOf...Is` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-105">Visual Basic provides two means of determining which type of object is stored in an object variable: the `TypeName` function and the `TypeOf...Is` operator.</span></span>  
  
## <a name="typename-and-typeofis"></a><span data-ttu-id="5a589-106">TypeName 및 TypeOf ... 되었습니다</span><span class="sxs-lookup"><span data-stu-id="5a589-106">TypeName and TypeOf…Is</span></span>  
 <span data-ttu-id="5a589-107">`TypeName`함수는 문자열을 반환 하며 다음 코드 조각과 같이 개체의 클래스 이름을 저장 하거나 표시 해야 하는 경우에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-107">The `TypeName` function returns a string and is the best choice when you need to store or display the class name of an object, as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#92](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#92)]  
  
 <span data-ttu-id="5a589-108">연산자는를 `TypeOf...Is` 사용 하 여 문자열을 비교 하는 것 보다 훨씬 빠르기 때문에 개체 형식을 테스트 하는 데 가장 적합 합니다 `TypeName` .</span><span class="sxs-lookup"><span data-stu-id="5a589-108">The `TypeOf...Is` operator is the best choice for testing an object's type, because it is much faster than an equivalent string comparison using `TypeName`.</span></span> <span data-ttu-id="5a589-109">다음 코드 조각에서는 `TypeOf...Is` 문 내에서를 사용 합니다 `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="5a589-109">The following code fragment uses `TypeOf...Is` within an `If...Then...Else` statement:</span></span>  
  
 [!code-vb[VbVbalrOOP#93](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#93)]  
  
 <span data-ttu-id="5a589-110">주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-110">A word of caution is due here.</span></span> <span data-ttu-id="5a589-111">`TypeOf...Is`연산자는 `True` 개체가 특정 형식 이거나 특정 형식에서 파생 된 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-111">The `TypeOf...Is` operator returns `True` if an object is of a specific type, or is derived from a specific type.</span></span> <span data-ttu-id="5a589-112">Visual Basic와 관련 하 여 수행 하는 거의 모든 작업에는 개체 (예: 문자열 및 정수)로 일반적으로 고려 되지 않는 일부 요소를 포함 하는 개체가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-112">Almost everything you do with Visual Basic involves objects, which include some elements not normally thought of as objects, such as strings and integers.</span></span> <span data-ttu-id="5a589-113">이러한 개체는에서 파생 되며에서 메서드를 상속 <xref:System.Object> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-113">These objects are derived from and inherit methods from <xref:System.Object>.</span></span> <span data-ttu-id="5a589-114">를 전달 `Integer` 하 고를 사용 하 여를 계산 하 `Object` 는 경우 연산자는을 `TypeOf...Is` 반환 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-114">When passed an `Integer` and evaluated with `Object`, the `TypeOf...Is` operator returns `True`.</span></span> <span data-ttu-id="5a589-115">다음 예제에서는 매개 변수가 및 임을 보고 합니다 `InParam` `Object` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="5a589-115">The following example reports that the parameter `InParam` is both an `Object` and an `Integer`:</span></span>  
  
 [!code-vb[VbVbalrOOP#94](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#94)]  
  
 <span data-ttu-id="5a589-116">다음 예제에서는 및를 모두 사용 하 여 `TypeOf...Is` `TypeName` 인수에 전달 된 개체의 형식을 확인 합니다 `Ctrl` .</span><span class="sxs-lookup"><span data-stu-id="5a589-116">The following example uses both `TypeOf...Is` and `TypeName` to determine the type of object passed to it in the `Ctrl` argument.</span></span> <span data-ttu-id="5a589-117">`TestObject`프로시저는 `ShowType` 세 가지 다른 종류의 컨트롤을 사용 하 여를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-117">The `TestObject` procedure calls `ShowType` with three different kinds of controls.</span></span>  
  
#### <a name="to-run-the-example"></a><span data-ttu-id="5a589-118">예제를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5a589-118">To run the example</span></span>  
  
1. <span data-ttu-id="5a589-119">새 Windows 응용 프로그램 프로젝트를 만들고 컨트롤 <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.CheckBox> 컨트롤 및 <xref:System.Windows.Forms.RadioButton> 컨트롤을 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-119">Create a new Windows Application project and add a <xref:System.Windows.Forms.Button> control, a <xref:System.Windows.Forms.CheckBox> control, and a <xref:System.Windows.Forms.RadioButton> control to the form.</span></span>  
  
2. <span data-ttu-id="5a589-120">폼의 단추에서 프로시저를 호출 `TestObject` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-120">From the button on your form, call the `TestObject` procedure.</span></span>  
  
3. <span data-ttu-id="5a589-121">폼에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a589-121">Add the following code to your form:</span></span>  
  
     [!code-vb[VbVbalrOOP#95](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#95)]  
  
## <a name="see-also"></a><span data-ttu-id="5a589-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a589-122">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.TypeName%2A>
- [<span data-ttu-id="5a589-123">문자열 이름을 사용하여 속성 또는 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="5a589-123">Calling a Property or Method Using a String Name</span></span>](calling-a-property-or-method-using-a-string-name.md)
- [<span data-ttu-id="5a589-124">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="5a589-124">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="5a589-125">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="5a589-125">If...Then...Else Statement</span></span>](../../../language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="5a589-126">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a589-126">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
- [<span data-ttu-id="5a589-127">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a589-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)
