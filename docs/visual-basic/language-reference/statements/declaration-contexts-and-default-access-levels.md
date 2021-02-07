---
description: 자세한 내용은 선언 컨텍스트 및 기본 액세스 수준 (Visual Basic)을 확인 하세요.
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
ms.openlocfilehash: c550db39862fbe9f69e5651b6e9fc7fdfcc88513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700340"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a><span data-ttu-id="2ada5-103">선언 컨텍스트 및 기본 액세스 수준(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ada5-103">Declaration Contexts and Default Access Levels (Visual Basic)</span></span>

<span data-ttu-id="2ada5-104">이 항목에서는 다른 형식 내에서 선언할 수 있는 Visual Basic 형식 및 지정 되지 않은 경우 기본적으로 사용 되는 액세스 수준에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-104">This topic describes which Visual Basic types can be declared within which other types, and what their access levels default to if not specified.</span></span>  
  
## <a name="declaration-context-levels"></a><span data-ttu-id="2ada5-105">선언 컨텍스트 수준</span><span class="sxs-lookup"><span data-stu-id="2ada5-105">Declaration Context Levels</span></span>  

 <span data-ttu-id="2ada5-106">프로그래밍 요소의 *선언 컨텍스트* 는 선언 된 코드 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-106">The *declaration context* of a programming element is the region of code in which it is declared.</span></span> <span data-ttu-id="2ada5-107">이는 일반적으로 *포함 하는 요소* 라고 하는 또 다른 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-107">This is often another programming element, which is then called the *containing element*.</span></span>  
  
 <span data-ttu-id="2ada5-108">선언 컨텍스트의 수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-108">The levels for declaration contexts are the following:</span></span>  
  
- <span data-ttu-id="2ada5-109">*네임 스페이스 수준* -소스 파일 또는 네임 스페이스 내에 있지만 클래스, 구조체, 모듈 또는 인터페이스에는 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-109">*Namespace level* — within a source file or namespace but not within a class, structure, module, or interface</span></span>  
  
- <span data-ttu-id="2ada5-110">*모듈 수준* -클래스, 구조체, 모듈 또는 인터페이스 내에서 프로시저나 블록 내에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-110">*Module level* — within a class, structure, module, or interface but not within a procedure or block</span></span>  
  
- <span data-ttu-id="2ada5-111">프로시저 *수준* -프로시저 또는 블록 내에서 (예: `If` 또는 `For` )</span><span class="sxs-lookup"><span data-stu-id="2ada5-111">*Procedure level* — within a procedure or block (such as `If` or `For`)</span></span>  
  
 <span data-ttu-id="2ada5-112">다음 표에서는 선언 컨텍스트에 따라 다양 하 게 선언 된 프로그래밍 요소에 대 한 기본 액세스 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ada5-112">The following table shows the default access levels for various declared programming elements, depending on their declaration contexts.</span></span>  
  
|<span data-ttu-id="2ada5-113">선언 요소</span><span class="sxs-lookup"><span data-stu-id="2ada5-113">Declared element</span></span>|<span data-ttu-id="2ada5-114">네임 스페이스 수준</span><span class="sxs-lookup"><span data-stu-id="2ada5-114">Namespace level</span></span>|<span data-ttu-id="2ada5-115">모듈 수준</span><span class="sxs-lookup"><span data-stu-id="2ada5-115">Module level</span></span>|<span data-ttu-id="2ada5-116">프로시저 수준</span><span class="sxs-lookup"><span data-stu-id="2ada5-116">Procedure level</span></span>|  
|----------------------|---------------------|------------------|---------------------|  
|<span data-ttu-id="2ada5-117">Variable ([Dim 문](dim-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-117">Variable ([Dim Statement](dim-statement.md))</span></span>|<span data-ttu-id="2ada5-118">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-118">Not allowed</span></span>|<span data-ttu-id="2ada5-119">`Private`에서는 `Public` `Structure` 허용 되지 않습니다. `Interface`</span><span class="sxs-lookup"><span data-stu-id="2ada5-119">`Private` (`Public` in `Structure`, not allowed in `Interface`)</span></span>|`Public`|  
|<span data-ttu-id="2ada5-120">상수 ([Const 문](const-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-120">Constant ([Const Statement](const-statement.md))</span></span>|<span data-ttu-id="2ada5-121">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-121">Not allowed</span></span>|<span data-ttu-id="2ada5-122">`Private`에서는 `Public` `Structure` 허용 되지 않습니다. `Interface`</span><span class="sxs-lookup"><span data-stu-id="2ada5-122">`Private` (`Public` in `Structure`, not allowed in `Interface`)</span></span>|`Public`|  
|<span data-ttu-id="2ada5-123">Enumeration ([Enum 문](enum-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-123">Enumeration ([Enum Statement](enum-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="2ada5-124">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-124">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-125">클래스 ([클래스 문](class-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-125">Class ([Class Statement](class-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="2ada5-126">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-126">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-127">Structure ([Structure 문](structure-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-127">Structure ([Structure Statement](structure-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="2ada5-128">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-128">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-129">Module ([Module 문](module-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-129">Module ([Module Statement](module-statement.md))</span></span>|`Friend`|<span data-ttu-id="2ada5-130">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-130">Not allowed</span></span>|<span data-ttu-id="2ada5-131">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-131">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-132">Interface ([Interface 문](interface-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-132">Interface ([Interface Statement](interface-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="2ada5-133">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-133">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-134">프로시저 ([Function 문](function-statement.md), [Sub 문](sub-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-134">Procedure ([Function Statement](function-statement.md), [Sub Statement](sub-statement.md))</span></span>|<span data-ttu-id="2ada5-135">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-135">Not allowed</span></span>|`Public`|<span data-ttu-id="2ada5-136">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-136">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-137">외부 참조 ([Declare 문](declare-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-137">External reference ([Declare Statement](declare-statement.md))</span></span>|<span data-ttu-id="2ada5-138">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-138">Not allowed</span></span>|<span data-ttu-id="2ada5-139">`Public` (에서 허용 되지 않음 `Interface` )</span><span class="sxs-lookup"><span data-stu-id="2ada5-139">`Public` (not allowed in `Interface`)</span></span>|<span data-ttu-id="2ada5-140">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-140">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-141">Operator ([Operator 문](operator-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-141">Operator ([Operator Statement](operator-statement.md))</span></span>|<span data-ttu-id="2ada5-142">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-142">Not allowed</span></span>|<span data-ttu-id="2ada5-143">`Public` (또는에서는 허용 되지 않음 `Interface` `Module` )</span><span class="sxs-lookup"><span data-stu-id="2ada5-143">`Public` (not allowed in `Interface` or `Module`)</span></span>|<span data-ttu-id="2ada5-144">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-144">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-145">Property ([Property 문](property-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-145">Property ([Property Statement](property-statement.md))</span></span>|<span data-ttu-id="2ada5-146">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-146">Not allowed</span></span>|`Public`|<span data-ttu-id="2ada5-147">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-147">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-148">Default 속성 ([기본값](../modifiers/default.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-148">Default property ([Default](../modifiers/default.md))</span></span>|<span data-ttu-id="2ada5-149">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-149">Not allowed</span></span>|<span data-ttu-id="2ada5-150">`Public` (에서 허용 되지 않음 `Module` )</span><span class="sxs-lookup"><span data-stu-id="2ada5-150">`Public` (not allowed in `Module`)</span></span>|<span data-ttu-id="2ada5-151">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-151">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-152">이벤트 ([Event Statement](event-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-152">Event ([Event Statement](event-statement.md))</span></span>|<span data-ttu-id="2ada5-153">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-153">Not allowed</span></span>|`Public`|<span data-ttu-id="2ada5-154">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-154">Not allowed</span></span>|  
|<span data-ttu-id="2ada5-155">Delegate ([Delegate 문](delegate-statement.md))</span><span class="sxs-lookup"><span data-stu-id="2ada5-155">Delegate ([Delegate Statement](delegate-statement.md))</span></span>|`Friend`|`Public`|<span data-ttu-id="2ada5-156">허용되지 않음</span><span class="sxs-lookup"><span data-stu-id="2ada5-156">Not allowed</span></span>|  
  
 <span data-ttu-id="2ada5-157">자세한 내용은 [Visual Basic의 액세스 수준](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ada5-157">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ada5-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ada5-158">See also</span></span>

- [<span data-ttu-id="2ada5-159">Friend</span><span class="sxs-lookup"><span data-stu-id="2ada5-159">Friend</span></span>](../modifiers/friend.md)
- [<span data-ttu-id="2ada5-160">개인</span><span class="sxs-lookup"><span data-stu-id="2ada5-160">Private</span></span>](../modifiers/private.md)
- [<span data-ttu-id="2ada5-161">공용</span><span class="sxs-lookup"><span data-stu-id="2ada5-161">Public</span></span>](../modifiers/public.md)
