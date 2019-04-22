---
title: 수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: a880ae8c13eebd5d9d325468098e058f58d3fa71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826667"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="e3b3c-102">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3b3c-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="e3b3c-103">프로시저를 호출 하는 경우 일반적으로에 하나 이상의 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="e3b3c-104">각 인수는 기본 프로그래밍 요소에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="e3b3c-105">인수 자체와 내부 요소에 모두 수정할 수 또는 수정할 수 없는 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="e3b3c-106">수정할 수 있는 인수와 수정할 수 없는 요소</span><span class="sxs-lookup"><span data-stu-id="e3b3c-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="e3b3c-107">프로그래밍 요소를 수 있습니다는 *수정할 수 있는 요소*, 변경 하 고, 해당 값을 사용할 수 있는 또는 *수정할 수 없는 요소*, 만들어진 후 있는 고정된 값.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="e3b3c-108">다음 표에서 수정할 수 있는 인수와 수정할 수 없는 프로그래밍 요소를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="e3b3c-109">수정할 수 있는 요소</span><span class="sxs-lookup"><span data-stu-id="e3b3c-109">Modifiable elements</span></span>|<span data-ttu-id="e3b3c-110">수정할 수 없는 요소</span><span class="sxs-lookup"><span data-stu-id="e3b3c-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="e3b3c-111">지역 변수 (프로시저 내에서 선언 됨), 읽기 전용으로 제외 하 고 개체 변수를 포함 하 여</span><span class="sxs-lookup"><span data-stu-id="e3b3c-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="e3b3c-112">읽기 전용 변수, 필드 및 속성</span><span class="sxs-lookup"><span data-stu-id="e3b3c-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="e3b3c-113">읽기 전용으로 제외 하 고 필드 (모듈, 클래스 및 구조체의 멤버 변수)</span><span class="sxs-lookup"><span data-stu-id="e3b3c-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="e3b3c-114">상수 및 리터럴</span><span class="sxs-lookup"><span data-stu-id="e3b3c-114">Constants and literals</span></span>|  
|<span data-ttu-id="e3b3c-115">읽기 전용으로 제외 하 고 속성</span><span class="sxs-lookup"><span data-stu-id="e3b3c-115">Properties, except for read-only</span></span>|<span data-ttu-id="e3b3c-116">열거형 멤버</span><span class="sxs-lookup"><span data-stu-id="e3b3c-116">Enumeration members</span></span>|  
|<span data-ttu-id="e3b3c-117">배열 요소</span><span class="sxs-lookup"><span data-stu-id="e3b3c-117">Array elements</span></span>|<span data-ttu-id="e3b3c-118">식 (해당 요소는 수정할 수 있는 경우에)</span><span class="sxs-lookup"><span data-stu-id="e3b3c-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="e3b3c-119">수정할 수 있는 인수와 수정할 수 없는 인수</span><span class="sxs-lookup"><span data-stu-id="e3b3c-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="e3b3c-120">A *수정할 수 있는 인수* 수정할 수 있는 기본 요소를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="e3b3c-121">호출 코드에서 언제 든 지 새 값을 저장할 수 있습니다 및 인수를 전달 하는 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), 프로시저의 코드 호출 코드의 내부 요소를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="e3b3c-122">A *수정할 수 없는 인수* 는 내부 요소를 수정할 수 없는 또는 전달 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="e3b3c-123">요소를 수정할 수 있는 경우에 프로시저에서 호출 코드의 내부 요소를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="e3b3c-124">요소를 수정할 수 없는 경우 자체 호출 코드를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="e3b3c-125">호출된 프로시저 수정 호출 코드의 내부 요소에 영향을 주지 않습니다 하지만 자체 로컬 복사본을 수정할 수 없는 인수를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b3c-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b3c-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3b3c-126">See also</span></span>

- [<span data-ttu-id="e3b3c-127">절차</span><span class="sxs-lookup"><span data-stu-id="e3b3c-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e3b3c-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="e3b3c-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e3b3c-129">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="e3b3c-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="e3b3c-130">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="e3b3c-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="e3b3c-131">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="e3b3c-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="e3b3c-132">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="e3b3c-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="e3b3c-133">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="e3b3c-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="e3b3c-134">방법: 인수가 값으로 전달 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="e3b3c-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="e3b3c-135">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="e3b3c-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="e3b3c-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="e3b3c-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
