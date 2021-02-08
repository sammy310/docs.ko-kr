---
description: '자세한 정보: End <keyword> 문 (Visual Basic)'
title: End <keyword> 문
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: ba21d4ba68a054d77d4f29307d49ed8e82bb6b50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769197"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="5b997-103">End \<keyword> 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b997-103">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="5b997-104">추가 키워드가 뒤에 나오면는 해당 키워드에 의해 도입 된 문 블록의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-104">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b997-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b997-105">Syntax</span></span>

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a><span data-ttu-id="5b997-106">부분</span><span class="sxs-lookup"><span data-stu-id="5b997-106">Parts</span></span>

|<span data-ttu-id="5b997-107">파트</span><span class="sxs-lookup"><span data-stu-id="5b997-107">Part</span></span>|<span data-ttu-id="5b997-108">설명</span><span class="sxs-lookup"><span data-stu-id="5b997-108">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="5b997-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-109">Required.</span></span> <span data-ttu-id="5b997-110">프로그래밍 요소의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-110">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="5b997-111">`AddHandler` `AddHandler` 사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 문에 의해 시작 된 접근자를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-111">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="5b997-112">일치 하는 [Class 문에](class-statement.md)의해 시작 된 클래스 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-112">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="5b997-113">일치 하는 [열거형 문에](enum-statement.md)의해 시작 된 열거형 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-113">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="5b997-114">`Custom`일치 하는 [이벤트 문에서](event-statement.md)시작한 이벤트 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-114">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="5b997-115">일치 하는 `Function` [함수 문에](function-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-115">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="5b997-116">실행 시 문이 발견 `End Function` 되 면 컨트롤이 호출 코드로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-116">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="5b997-117">`Property`일치 하는 [Get 문에](get-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-117">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="5b997-118">실행 시 문이 발생 하면 `End Get` 속성 값을 요청 하는 문으로 제어가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-118">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="5b997-119">을 (를) 종료 `If` 하는 `Then` 데 필요 합니다. ...`Else` 일치 하는 문에 의해 시작 된 블록 정의 `If` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-119">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="5b997-120">다음 [을 참조 하세요. 그런 다음 ... Else 문](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b997-120">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="5b997-121">일치 하는 [인터페이스 문에](interface-statement.md)의해 시작 된 인터페이스 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-121">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="5b997-122">일치 하는 [Module 문에](module-statement.md)의해 시작 된 모듈 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-122">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="5b997-123">일치 하는 [네임 스페이스 문에](namespace-statement.md)의해 시작 된 네임 스페이스 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-123">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="5b997-124">일치 하는 [Operator 문에](operator-statement.md)의해 시작 된 연산자 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-124">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="5b997-125">일치 하는 [속성 문에](property-statement.md)의해 시작 된 속성 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-125">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="5b997-126">`RaiseEvent` `RaiseEvent` 사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 문에 의해 시작 된 접근자를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-126">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="5b997-127">`RemoveHandler` `RemoveHandler` 사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 문에 의해 시작 된 접근자를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-127">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="5b997-128">일치 하는 `Select` `Case` 문에 의해 시작 된 ... 블록 정의를 종료 하는 데 필요 합니다. `Select`</span><span class="sxs-lookup"><span data-stu-id="5b997-128">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="5b997-129">Select ...를 참조 하세요. [ Case 문](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b997-129">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="5b997-130">일치 하는 `Property` [Set 문에](set-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-130">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="5b997-131">실행 시 문이 발생 하면 `End Set` 컨트롤에서 속성 값을 설정 하는 문으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-131">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="5b997-132">일치 하는 [Structure 문에](structure-statement.md)의해 시작 된 구조 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-132">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="5b997-133">일치 하는 `Sub` [Sub 문에](sub-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-133">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="5b997-134">실행 시 문이 발견 `End Sub` 되 면 컨트롤이 호출 코드로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-134">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="5b997-135">일치 하는 문에 의해 시작 된 블록 정의를 종료 하는 데 필요 `SyncLock` `SyncLock` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-135">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="5b997-136">[SyncLock 문](synclock-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b997-136">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="5b997-137">을 (를) 종료 `Try` 하는 `Catch` 데 필요 합니다. ...`Finally` 일치 하는 문에 의해 시작 된 블록 정의 `Try` 입니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-137">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="5b997-138">[Try ... Catch ... Finally 문](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5b997-138">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="5b997-139">일치 하는 문에 의해 시작 된 루프 정의를 종료 하는 데 필요 `While` `While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-139">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="5b997-140">잠시 보기 ... [ End While 문](while-end-while-statement.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-140">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="5b997-141">일치 하는 문에 의해 시작 된 블록 정의를 종료 하는 데 필요 `With` `With` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-141">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="5b997-142">다음 [으로 보기 ... End With 문](with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="5b997-142">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="5b997-143">지시문</span><span class="sxs-lookup"><span data-stu-id="5b997-143">Directives</span></span>

<span data-ttu-id="5b997-144">숫자 기호 () 뒤에 오는 `#` `End` 키워드는 해당 지시문에 의해 도입 된 전처리 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-144">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="5b997-145">파트</span><span class="sxs-lookup"><span data-stu-id="5b997-145">Part</span></span>|<span data-ttu-id="5b997-146">설명</span><span class="sxs-lookup"><span data-stu-id="5b997-146">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="5b997-147">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-147">Required.</span></span> <span data-ttu-id="5b997-148">전처리 블록의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-148">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="5b997-149">일치 하는 [#ExternalSource 지시문](../directives/externalsource-directive.md)에 의해 시작 되는 외부 소스 블록을 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-149">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="5b997-150">일치 하는 지시문에 의해 시작 된 조건부 컴파일 블록을 종료 하는 데 필요 `#If` 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-150">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="5b997-151">#If를 참조 하세요. [ Then ... #Else 지시문](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="5b997-151">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="5b997-152">일치 하는 [#Region 지시문](../directives/region-directive.md)에 의해 시작 된 소스 영역 블록을 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-152">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="5b997-153">설명</span><span class="sxs-lookup"><span data-stu-id="5b997-153">Remarks</span></span>

<span data-ttu-id="5b997-154">[End 문은](end-statement.md)추가 키워드가 없으면 실행을 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-154">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="5b997-155">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="5b997-155">Smart Device Developer Notes</span></span>  

<span data-ttu-id="5b997-156">`End`추가 키워드가 없는 문은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b997-156">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b997-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b997-157">See also</span></span>

- [<span data-ttu-id="5b997-158">End 문</span><span class="sxs-lookup"><span data-stu-id="5b997-158">End Statement</span></span>](end-statement.md)
