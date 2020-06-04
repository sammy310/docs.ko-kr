---
title: 선언 컨텍스트 및 기본 액세스 수준
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: b5bb943a062ac648f88645fb6de1acb42213071c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404799"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a><span data-ttu-id="88c92-102">선언 컨텍스트 및 기본 액세스 수준(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88c92-102">Declaration Contexts and Default Access Levels (Visual Basic)</span></span>
<span data-ttu-id="88c92-103">이 항목에서는 다른 형식 내에서 선언할 수 있는 Visual Basic 형식 및 지정 되지 않은 경우 기본적으로 사용 되는 액세스 수준에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-103">This topic describes which Visual Basic types can be declared within which other types, and what their access levels default to if not specified.</span></span>  
  
## <a name="declaration-context-levels"></a><span data-ttu-id="88c92-104">선언 컨텍스트 수준</span><span class="sxs-lookup"><span data-stu-id="88c92-104">Declaration Context Levels</span></span>  
 <span data-ttu-id="88c92-105">프로그래밍 요소의 *선언 컨텍스트* 는 선언 된 코드 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-105">The *declaration context* of a programming element is the region of code in which it is declared.</span></span> <span data-ttu-id="88c92-106">이는 일반적으로 *포함 하는 요소*라고 하는 또 다른 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-106">This is often another programming element, which is then called the *containing element*.</span></span>  
  
 <span data-ttu-id="88c92-107">선언 컨텍스트의 수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-107">The levels for declaration contexts are the following:</span></span>  
  
- <span data-ttu-id="88c92-108">*네임 스페이스 수준* -소스 파일 또는 네임 스페이스 내에 있지만 클래스, 구조체, 모듈 또는 인터페이스에는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-108">*Namespace level* — within a source file or namespace but not within a class, structure, module, or interface</span></span>  
  
- <span data-ttu-id="88c92-109">*모듈 수준* -클래스, 구조체, 모듈 또는 인터페이스 내에서 프로시저나 블록 내에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-109">*Module level* — within a class, structure, module, or interface but not within a procedure or block</span></span>  
  
- <span data-ttu-id="88c92-110">프로시저 *수준* -프로시저 또는 블록 내에서 (예: `If` 또는 `For` )</span><span class="sxs-lookup"><span data-stu-id="88c92-110">*Procedure level* — within a procedure or block (such as `If` or `For`)</span></span>  
  
 <span data-ttu-id="88c92-111">다음 표에서는 선언 컨텍스트에 따라 다양 하 게 선언 된 프로그래밍 요소에 대 한 기본 액세스 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88c92-111">The following table shows the default access levels for various declared programming elements, depending on their declaration contexts.</span></span>  
  
|<span data-ttu-id="88c92-112">선언 요소</span><span class="sxs-lookup"><span data-stu-id="88c92-112">Declared element</span></span>|<span data-ttu-id="88c92-113">네임 스페이스 수준</span><span class="sxs-lookup"><span data-stu-id="88c92-113">Namespace level</span></span>|<span data-ttu-id="88c92-114">모듈 수준</span><span class="sxs-lookup"><span data-stu-id="88c92-114">Module level</span></span>|<span data-ttu-id="88c92-115">프로시저 수준</span><span class="sxs-lookup"><span data-stu-id="88c92-115">Procedure level</span></span>|  
|----------------------|---------------------|------------------|---------------------|  
|<span data-ttu-id="88c92-116">Variable ([Dim 문](dim-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-116">Variable ([Dim Statement](dim-statement.md))</span></span>|<span data-ttu-id="88c92-117">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-117">Not allowed</span></span>|<span data-ttu-id="88c92-118">`Private`에서는 `Public` `Structure` 허용 되지 않습니다. `Interface`</span><span class="sxs-lookup"><span data-stu-id="88c92-118">`Private` (`Public` in `Structure`, not allowed in `Interface`)</span></span>|`Public`|  
|<span data-ttu-id="88c92-119">상수 ([Const 문](const-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-119">Constant ([Const Statement](const-statement.md))</span></span>|<span data-ttu-id="88c92-120">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-120">Not allowed</span></span>|<span data-ttu-id="88c92-121">`Private`에서는 `Public` `Structure` 허용 되지 않습니다. `Interface`</span><span class="sxs-lookup"><span data-stu-id="88c92-121">`Private` (`Public` in `Structure`, not allowed in `Interface`)</span></span>|`Public`|  
|<span data-ttu-id="88c92-122">Enumeration ([Enum 문](enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-122">Enumeration ([Enum Statement](enum-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="88c92-123">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-123">Not allowed</span></span>|  
|<span data-ttu-id="88c92-124">클래스 ([클래스 문](class-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-124">Class ([Class Statement](class-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="88c92-125">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-125">Not allowed</span></span>|  
|<span data-ttu-id="88c92-126">Structure ([Structure 문](structure-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-126">Structure ([Structure Statement](structure-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="88c92-127">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-127">Not allowed</span></span>|  
|<span data-ttu-id="88c92-128">Module ([Module 문](module-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-128">Module ([Module Statement](module-statement.md))</span></span>|`Friend`|<span data-ttu-id="88c92-129">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-129">Not allowed</span></span>|<span data-ttu-id="88c92-130">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-130">Not allowed</span></span>|  
|<span data-ttu-id="88c92-131">Interface ([Interface 문](interface-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-131">Interface ([Interface Statement](interface-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="88c92-132">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-132">Not allowed</span></span>|  
|<span data-ttu-id="88c92-133">프로시저 ([Function 문](function-statement.md), [Sub 문](sub-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-133">Procedure ([Function Statement](function-statement.md), [Sub Statement](sub-statement.md))</span></span>|<span data-ttu-id="88c92-134">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-134">Not allowed</span></span>|`Public`|<span data-ttu-id="88c92-135">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-135">Not allowed</span></span>|  
|<span data-ttu-id="88c92-136">외부 참조 ([Declare 문](declare-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-136">External reference ([Declare Statement](declare-statement.md))</span></span>|<span data-ttu-id="88c92-137">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-137">Not allowed</span></span>|<span data-ttu-id="88c92-138">`Public`(에서 허용 되지 않음 `Interface` )</span><span class="sxs-lookup"><span data-stu-id="88c92-138">`Public` (not allowed in `Interface`)</span></span>|<span data-ttu-id="88c92-139">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-139">Not allowed</span></span>|  
|<span data-ttu-id="88c92-140">Operator ([Operator 문](operator-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-140">Operator ([Operator Statement](operator-statement.md))</span></span>|<span data-ttu-id="88c92-141">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-141">Not allowed</span></span>|<span data-ttu-id="88c92-142">`Public`(또는에서는 허용 되지 않음 `Interface` `Module` )</span><span class="sxs-lookup"><span data-stu-id="88c92-142">`Public` (not allowed in `Interface` or `Module`)</span></span>|<span data-ttu-id="88c92-143">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-143">Not allowed</span></span>|  
|<span data-ttu-id="88c92-144">Property ([Property 문](property-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-144">Property ([Property Statement](property-statement.md))</span></span>|<span data-ttu-id="88c92-145">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-145">Not allowed</span></span>|`Public`|<span data-ttu-id="88c92-146">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-146">Not allowed</span></span>|  
|<span data-ttu-id="88c92-147">Default 속성 ([기본값](../modifiers/default.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-147">Default property ([Default](../modifiers/default.md))</span></span>|<span data-ttu-id="88c92-148">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-148">Not allowed</span></span>|<span data-ttu-id="88c92-149">`Public`(에서 허용 되지 않음 `Module` )</span><span class="sxs-lookup"><span data-stu-id="88c92-149">`Public` (not allowed in `Module`)</span></span>|<span data-ttu-id="88c92-150">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-150">Not allowed</span></span>|  
|<span data-ttu-id="88c92-151">이벤트 ([Event Statement](event-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-151">Event ([Event Statement](event-statement.md))</span></span>|<span data-ttu-id="88c92-152">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-152">Not allowed</span></span>|`Public`|<span data-ttu-id="88c92-153">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-153">Not allowed</span></span>|  
|<span data-ttu-id="88c92-154">Delegate ([Delegate 문](delegate-statement.md))</span><span class="sxs-lookup"><span data-stu-id="88c92-154">Delegate ([Delegate Statement](delegate-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="88c92-155">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="88c92-155">Not allowed</span></span>|  
  
 <span data-ttu-id="88c92-156">자세한 내용은 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88c92-156">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c92-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88c92-157">See also</span></span>

- [<span data-ttu-id="88c92-158">Friend</span><span class="sxs-lookup"><span data-stu-id="88c92-158">Friend</span></span>](../modifiers/friend.md)
- [<span data-ttu-id="88c92-159">프라이빗</span><span class="sxs-lookup"><span data-stu-id="88c92-159">Private</span></span>](../modifiers/private.md)
- [<span data-ttu-id="88c92-160">공용</span><span class="sxs-lookup"><span data-stu-id="88c92-160">Public</span></span>](../modifiers/public.md)
