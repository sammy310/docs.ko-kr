---
title: End <keyword> 문
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: 87f4724cc036e6e0bdf0b558854a4034f45b9ab5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343742"
---
# <a name="end-keyword-statement-visual-basic"></a><span data-ttu-id="b43c4-102">End \<keyword > 문 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b43c4-102">End \<keyword> Statement (Visual Basic)</span></span>

<span data-ttu-id="b43c4-103">추가 키워드가 뒤에 나오면는 해당 키워드에 의해 도입 된 문 블록의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-103">When followed by an additional keyword, terminates the definition of the statement block introduced by that keyword.</span></span>

## <a name="syntax"></a><span data-ttu-id="b43c4-104">구문</span><span class="sxs-lookup"><span data-stu-id="b43c4-104">Syntax</span></span>

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
  
## <a name="parts"></a><span data-ttu-id="b43c4-105">요소</span><span class="sxs-lookup"><span data-stu-id="b43c4-105">Parts</span></span>

|<span data-ttu-id="b43c4-106">파트</span><span class="sxs-lookup"><span data-stu-id="b43c4-106">Part</span></span>|<span data-ttu-id="b43c4-107">설명</span><span class="sxs-lookup"><span data-stu-id="b43c4-107">Description</span></span>|
|---|---|
|`End`|<span data-ttu-id="b43c4-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-108">Required.</span></span> <span data-ttu-id="b43c4-109">프로그래밍 요소의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-109">Terminates the definition of the programming element.</span></span>|
|`AddHandler`|<span data-ttu-id="b43c4-110">사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 `AddHandler` 문에 의해 시작 된 `AddHandler` 접근자를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-110">Required to terminate an `AddHandler` accessor begun by a matching `AddHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Class`|<span data-ttu-id="b43c4-111">일치 하는 [Class 문에](class-statement.md)의해 시작 된 클래스 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-111">Required to terminate a class definition begun by a matching [Class Statement](class-statement.md).</span></span>|
|`Enum`|<span data-ttu-id="b43c4-112">일치 하는 [열거형 문에](enum-statement.md)의해 시작 된 열거형 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-112">Required to terminate an enumeration definition begun by a matching [Enum Statement](enum-statement.md).</span></span>|
|`Event`|<span data-ttu-id="b43c4-113">일치 하는 [이벤트 문에](event-statement.md)의해 시작 된 `Custom` 이벤트 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-113">Required to terminate a `Custom` event definition begun by a matching [Event Statement](event-statement.md).</span></span>|  
|`Function`|<span data-ttu-id="b43c4-114">일치 하는 [함수 문에](function-statement.md)의해 시작 된 `Function` 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-114">Required to terminate a `Function` procedure definition begun by a matching [Function Statement](function-statement.md).</span></span> <span data-ttu-id="b43c4-115">실행 시 `End Function` 문이 발견 되 면 컨트롤이 호출 코드로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-115">If execution encounters an `End Function` statement, control returns to the calling code.</span></span>|
|`Get`|<span data-ttu-id="b43c4-116">일치 하는 [Get 문에](get-statement.md)의해 시작 된 `Property` 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-116">Required to terminate a `Property` procedure definition begun by a matching [Get Statement](get-statement.md).</span></span> <span data-ttu-id="b43c4-117">실행에 `End Get` 문이 있으면 속성의 값을 요청 하는 문으로 제어가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-117">If execution encounters an `End Get` statement, control returns to the statement requesting the property's value.</span></span>|
|`If`|<span data-ttu-id="b43c4-118">일치 하는 `If` 문에 의해 시작 된 `If`...`Then`...`Else` 블록 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-118">Required to terminate an `If`...`Then`...`Else` block definition begun by a matching `If` statement.</span></span> <span data-ttu-id="b43c4-119">다음 [을 참조 하세요. 그런 다음 ... Else 문](if-then-else-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b43c4-119">See [If...Then...Else Statement](if-then-else-statement.md).</span></span>|
|`Interface`|<span data-ttu-id="b43c4-120">일치 하는 [인터페이스 문에](interface-statement.md)의해 시작 된 인터페이스 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-120">Required to terminate an interface definition begun by a matching [Interface Statement](interface-statement.md).</span></span>|
|`Module`|<span data-ttu-id="b43c4-121">일치 하는 [Module 문에](module-statement.md)의해 시작 된 모듈 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-121">Required to terminate a module definition begun by a matching [Module Statement](module-statement.md).</span></span>|
|`Namespace`|<span data-ttu-id="b43c4-122">일치 하는 [네임 스페이스 문에](namespace-statement.md)의해 시작 된 네임 스페이스 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-122">Required to terminate a namespace definition begun by a matching [Namespace Statement](namespace-statement.md).</span></span>|
|`Operator`|<span data-ttu-id="b43c4-123">일치 하는 [Operator 문에](operator-statement.md)의해 시작 된 연산자 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-123">Required to terminate an operator definition begun by a matching [Operator Statement](operator-statement.md).</span></span>|
|`Property`|<span data-ttu-id="b43c4-124">일치 하는 [속성 문에](property-statement.md)의해 시작 된 속성 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-124">Required to terminate a property definition begun by a matching [Property Statement](property-statement.md).</span></span>|
|`RaiseEvent`|<span data-ttu-id="b43c4-125">사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 `RaiseEvent` 문에 의해 시작 된 `RaiseEvent` 접근자를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-125">Required to terminate a `RaiseEvent` accessor begun by a matching `RaiseEvent` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`RemoveHandler`|<span data-ttu-id="b43c4-126">사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 `RemoveHandler` 문에 의해 시작 된 `RemoveHandler` 접근자를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-126">Required to terminate a `RemoveHandler` accessor begun by a matching `RemoveHandler` statement in a custom [Event Statement](event-statement.md).</span></span>|
|`Select`|<span data-ttu-id="b43c4-127">일치 하는 `Select` 문에 의해 시작 된 `Select``Case` 블록 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-127">Required to terminate a `Select`...`Case` block definition begun by a matching `Select` statement.</span></span> <span data-ttu-id="b43c4-128">Select ...를 참조 하세요. [ Case 문](select-case-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b43c4-128">See [Select...Case Statement](select-case-statement.md).</span></span>  
|`Set`|<span data-ttu-id="b43c4-129">일치 하는 [Set 문에](set-statement.md)의해 시작 된 `Property` 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-129">Required to terminate a `Property` procedure definition begun by a matching [Set Statement](set-statement.md).</span></span> <span data-ttu-id="b43c4-130">실행 시 `End Set` 문이 발견 되 면 컨트롤은 속성의 값을 설정 하는 문으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-130">If execution encounters an `End Set` statement, control returns to the statement setting the property's value.</span></span>  
|`Structure`|<span data-ttu-id="b43c4-131">일치 하는 [Structure 문에](structure-statement.md)의해 시작 된 구조 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-131">Required to terminate a structure definition begun by a matching [Structure Statement](structure-statement.md).</span></span>  
|`Sub`|<span data-ttu-id="b43c4-132">일치 하는 [Sub 문에](sub-statement.md)의해 시작 된 `Sub` 프로시저 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-132">Required to terminate a `Sub` procedure definition begun by a matching [Sub Statement](sub-statement.md).</span></span> <span data-ttu-id="b43c4-133">실행 시 `End Sub` 문이 발견 되 면 컨트롤이 호출 코드로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-133">If execution encounters an `End Sub` statement, control returns to the calling code.</span></span>  
|`SyncLock`|<span data-ttu-id="b43c4-134">일치 하는 `SyncLock` 문에 의해 시작 된 `SyncLock` 블록 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-134">Required to terminate a `SyncLock` block definition begun by a matching `SyncLock` statement.</span></span> <span data-ttu-id="b43c4-135">[SyncLock 문](synclock-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b43c4-135">See [SyncLock Statement](synclock-statement.md).</span></span>  
|`Try`|<span data-ttu-id="b43c4-136">일치 하는 `Try` 문에 의해 시작 된 `Try`...`Catch`...`Finally` 블록 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-136">Required to terminate a `Try`...`Catch`...`Finally` block definition begun by a matching `Try` statement.</span></span> <span data-ttu-id="b43c4-137">[Try ... Catch ... Finally 문](try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b43c4-137">See [Try...Catch...Finally Statement](try-catch-finally-statement.md).</span></span>  
|`While`|<span data-ttu-id="b43c4-138">일치 하는 `While` 문에 의해 시작 된 `While` 루프 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-138">Required to terminate a `While` loop definition begun by a matching `While` statement.</span></span> <span data-ttu-id="b43c4-139">잠시 보기 ... [ End While 문](while-end-while-statement.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-139">See [While...End While Statement](while-end-while-statement.md).</span></span>  
|`With`| <span data-ttu-id="b43c4-140">일치 하는 `With` 문에 의해 시작 된 `With` 블록 정의를 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-140">Required to terminate a `With` block definition begun by a matching `With` statement.</span></span> <span data-ttu-id="b43c4-141">다음 [으로 보기 ... End With 문](with-end-with-statement.md)</span><span class="sxs-lookup"><span data-stu-id="b43c4-141">See [With...End With Statement](with-end-with-statement.md).</span></span>  
|||
  
## <a name="directives"></a><span data-ttu-id="b43c4-142">지시문</span><span class="sxs-lookup"><span data-stu-id="b43c4-142">Directives</span></span>

<span data-ttu-id="b43c4-143">숫자 기호 (`#`) 뒤에 오는 `End` 키워드는 해당 지시문에 의해 도입 된 전처리 블록을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-143">When preceded by a number sign (`#`), the `End` keyword terminates a preprocessing block introduced by the corresponding directive.</span></span>  

```vb
#End ExternalSource
#End If
#End Region
```

|<span data-ttu-id="b43c4-144">파트</span><span class="sxs-lookup"><span data-stu-id="b43c4-144">Part</span></span>|<span data-ttu-id="b43c4-145">설명</span><span class="sxs-lookup"><span data-stu-id="b43c4-145">Description</span></span>|
|---|---|
|`#End`|<span data-ttu-id="b43c4-146">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-146">Required.</span></span> <span data-ttu-id="b43c4-147">전처리 블록의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-147">Terminates the definition of the preprocessing block.</span></span>|
|`ExternalSource`|<span data-ttu-id="b43c4-148">일치 하는 [#ExternalSource 지시문](../directives/externalsource-directive.md)에 의해 시작 되는 외부 소스 블록을 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-148">Required to terminate an external source block begun by a matching [#ExternalSource Directive](../directives/externalsource-directive.md).</span></span>|
|`If`|<span data-ttu-id="b43c4-149">일치 하는 `#If` 지시문에 의해 시작 된 조건부 컴파일 블록을 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-149">Required to terminate a conditional compilation block begun by a matching `#If` directive.</span></span> <span data-ttu-id="b43c4-150">#If를 참조 하세요. [ Then ... #Else 지시문](../directives/if-then-else-directives.md).</span><span class="sxs-lookup"><span data-stu-id="b43c4-150">See [#If...Then...#Else Directives](../directives/if-then-else-directives.md).</span></span>|
|`Region`|<span data-ttu-id="b43c4-151">일치 하는 [#Region 지시문](../directives/region-directive.md)에 의해 시작 된 소스 영역 블록을 종료 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-151">Required to terminate a source region block begun by a matching [#Region Directive](../directives/region-directive.md).</span></span>|
|||

## <a name="remarks"></a><span data-ttu-id="b43c4-152">주의</span><span class="sxs-lookup"><span data-stu-id="b43c4-152">Remarks</span></span>

<span data-ttu-id="b43c4-153">[End 문은](end-statement.md)추가 키워드가 없으면 실행을 즉시 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-153">The [End Statement](end-statement.md), without an additional keyword, terminates execution immediately.</span></span>

## <a name="smart-device-developer-notes"></a><span data-ttu-id="b43c4-154">스마트 디바이스 개발자 노트</span><span class="sxs-lookup"><span data-stu-id="b43c4-154">Smart Device Developer Notes</span></span>  

<span data-ttu-id="b43c4-155">추가 키워드가 없는 `End` 문은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b43c4-155">The `End` statement, without an additional keyword, is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43c4-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b43c4-156">See also</span></span>

- [<span data-ttu-id="b43c4-157">End 문</span><span class="sxs-lookup"><span data-stu-id="b43c4-157">End Statement</span></span>](end-statement.md)
