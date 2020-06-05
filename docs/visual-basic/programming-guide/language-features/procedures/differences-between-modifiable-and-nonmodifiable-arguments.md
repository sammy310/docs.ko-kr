---
title: 수정할 수 있는 인수와 수정할 수 없는 인수의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 733f92cc2cdaa6e923c57649774ceb64de172c18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403345"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="2a068-102">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a068-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="2a068-103">프로시저를 호출 하는 경우 일반적으로 하나 이상의 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="2a068-104">각 인수는 기본 프로그래밍 요소에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="2a068-105">기본 요소와 인수 자체는 수정할 수 있거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="2a068-106">수정 가능 하 고 수정할 요소가 없는 요소</span><span class="sxs-lookup"><span data-stu-id="2a068-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="2a068-107">프로그래밍 요소는 해당 값이 변경 될 수 있는 *수정 가능한 요소*이거나, 만들어진 후 고정 값이 있는 수정할 수 없는 *요소*일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="2a068-108">다음 표에서는 수정 및 수정할 때의 프로그래밍 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="2a068-109">수정 가능한 요소</span><span class="sxs-lookup"><span data-stu-id="2a068-109">Modifiable elements</span></span>|<span data-ttu-id="2a068-110">수정할 때 요소</span><span class="sxs-lookup"><span data-stu-id="2a068-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="2a068-111">읽기 전용을 제외 하 고 개체 변수를 포함 하 여 지역 변수 (프로시저 내에 선언 됨)</span><span class="sxs-lookup"><span data-stu-id="2a068-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="2a068-112">읽기 전용 변수, 필드 및 속성</span><span class="sxs-lookup"><span data-stu-id="2a068-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="2a068-113">필드 (모듈, 클래스 및 구조체의 멤버 변수) (읽기 전용 제외)</span><span class="sxs-lookup"><span data-stu-id="2a068-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="2a068-114">상수 및 리터럴</span><span class="sxs-lookup"><span data-stu-id="2a068-114">Constants and literals</span></span>|  
|<span data-ttu-id="2a068-115">읽기 전용을 제외한 속성</span><span class="sxs-lookup"><span data-stu-id="2a068-115">Properties, except for read-only</span></span>|<span data-ttu-id="2a068-116">열거형 멤버</span><span class="sxs-lookup"><span data-stu-id="2a068-116">Enumeration members</span></span>|  
|<span data-ttu-id="2a068-117">배열 요소</span><span class="sxs-lookup"><span data-stu-id="2a068-117">Array elements</span></span>|<span data-ttu-id="2a068-118">식 (요소를 수정할 수 있는 경우에도)</span><span class="sxs-lookup"><span data-stu-id="2a068-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="2a068-119">수정 가능 하 고 수정 가능한 인수</span><span class="sxs-lookup"><span data-stu-id="2a068-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="2a068-120">*수정 가능한 인수* 는 수정 가능한 기본 요소를 포함 하는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="2a068-121">호출 코드는 언제 든 지 새 값을 저장할 수 있으며, [ByRef](../../../language-reference/modifiers/byref.md)인수를 전달 하는 경우 프로시저의 코드는 호출 코드의 내부 요소를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="2a068-122">수정할 수 없는 *인수* 에는 수정할 수 없는 내부 요소가 있거나 [ByVal](../../../language-reference/modifiers/byval.md)로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="2a068-123">이 프로시저는 수정 가능한 요소인 경우에도 호출 코드의 기본 요소를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="2a068-124">수정할 수 없는 요소인 경우 호출 코드 자체에서 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="2a068-125">호출 된 프로시저는 수정할 수 없는 인수의 로컬 복사본을 수정할 수 있지만이 수정 작업은 호출 코드의 기본 요소에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a068-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a068-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a068-126">See also</span></span>

- [<span data-ttu-id="2a068-127">절차</span><span class="sxs-lookup"><span data-stu-id="2a068-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2a068-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="2a068-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2a068-129">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="2a068-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="2a068-130">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="2a068-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="2a068-131">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="2a068-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="2a068-132">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="2a068-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="2a068-133">방법: 값 변경으로부터 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="2a068-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="2a068-134">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="2a068-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="2a068-135">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="2a068-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="2a068-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="2a068-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
