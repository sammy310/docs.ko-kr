---
title: '방법: 속성 값 입력'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: 7d85066d4678ee2a53b8339bee2db20374482579
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071406"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="f69b6-102">방법: 속성 값 입력(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f69b6-102">How to: Put a Value in a Property (Visual Basic)</span></span>

<span data-ttu-id="f69b6-103">속성 이름을 대입문의 왼쪽에 배치 하 여 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="f69b6-104">속성 프로시저는 `Set` 값을 저장 하지만 이름으로 명시적으로 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="f69b6-105">변수를 사용 하는 것 처럼 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="f69b6-106">Visual Basic은 속성의 프로시저에 대 한 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="f69b6-107">속성에 값을 저장 하려면</span><span class="sxs-lookup"><span data-stu-id="f69b6-107">To store a value in a property</span></span>  
  
1. <span data-ttu-id="f69b6-108">대입문의 왼쪽에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="f69b6-109">다음 예제에서는 Visual Basic 속성의 값을 `TimeOfDay` 정오로 설정 하 여 해당 프로시저를 암시적으로 호출 합니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="f69b6-109">The following example sets the value of the Visual Basic `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="f69b6-110">속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-110">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f69b6-111">인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-111">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="f69b6-112">인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-112">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f69b6-113">속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-113">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4. <span data-ttu-id="f69b6-114">대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f69b6-114">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69b6-115">참조</span><span class="sxs-lookup"><span data-stu-id="f69b6-115">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [<span data-ttu-id="f69b6-116">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="f69b6-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="f69b6-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="f69b6-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f69b6-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="f69b6-118">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="f69b6-119">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="f69b6-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="f69b6-120">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="f69b6-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="f69b6-121">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="f69b6-121">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="f69b6-122">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="f69b6-122">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="f69b6-123">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="f69b6-123">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="f69b6-124">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="f69b6-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
