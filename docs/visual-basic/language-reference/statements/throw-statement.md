---
description: '자세한 정보: Throw 문 (Visual Basic)'
title: Throw 문
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: b7fa4183b5997e5dac8045502a8eed1afe66fc0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740940"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="0b353-103">Throw 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b353-103">Throw Statement (Visual Basic)</span></span>

<span data-ttu-id="0b353-104">프로시저 내에서 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b353-104">Throws an exception within a procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b353-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b353-105">Syntax</span></span>

```vb
Throw [ expression ]
```

## <a name="part"></a><span data-ttu-id="0b353-106">파트</span><span class="sxs-lookup"><span data-stu-id="0b353-106">Part</span></span>

`expression`\
<span data-ttu-id="0b353-107">Throw 되는 예외에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b353-107">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="0b353-108">문에 있으면 선택 사항이 고 `Catch` , 그렇지 않으면 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="0b353-108">Optional when residing in a `Catch` statement, otherwise required.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b353-109">설명</span><span class="sxs-lookup"><span data-stu-id="0b353-109">Remarks</span></span>

<span data-ttu-id="0b353-110">`Throw`문은 구조화 된 예외 처리 코드로 처리할 수 있는 예외를 throw 합니다 ( `Try` ... `Catch` ...`Finally`) 또는 비구조적 예외 처리 코드 ( `On Error GoTo` )</span><span class="sxs-lookup"><span data-stu-id="0b353-110">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="0b353-111">`Throw`Visual Basic은 적절 한 예외 처리 코드를 찾을 때까지 호출 스택 위로 이동 하기 때문에 문을 사용 하 여 코드 내에서 오류를 트래핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b353-111">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>

<span data-ttu-id="0b353-112">`Throw`식이 없는 문은 문에서만 사용할 수 있으며 `Catch` ,이 경우 문은 문에 의해 현재 처리 되 고 있는 예외를 다시 throw 합니다 `Catch` .</span><span class="sxs-lookup"><span data-stu-id="0b353-112">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>

<span data-ttu-id="0b353-113">`Throw`문은 예외에 대 한 호출 스택을 다시 설정 합니다 `expression` .</span><span class="sxs-lookup"><span data-stu-id="0b353-113">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="0b353-114">`expression`을 지정 하지 않으면 호출 스택이 변경 되지 않고 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b353-114">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="0b353-115">속성을 통해 예외에 대 한 호출 스택에 액세스할 수 있습니다 <xref:System.Exception.StackTrace%2A> .</span><span class="sxs-lookup"><span data-stu-id="0b353-115">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="0b353-116">예제</span><span class="sxs-lookup"><span data-stu-id="0b353-116">Example</span></span>

<span data-ttu-id="0b353-117">다음 코드에서는 문을 사용 하 여 `Throw` 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b353-117">The following code uses the `Throw` statement to throw an exception:</span></span>

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a><span data-ttu-id="0b353-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b353-118">See also</span></span>

- [<span data-ttu-id="0b353-119">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="0b353-119">Try...Catch...Finally Statement</span></span>](try-catch-finally-statement.md)
- [<span data-ttu-id="0b353-120">On Error 문</span><span class="sxs-lookup"><span data-stu-id="0b353-120">On Error Statement</span></span>](on-error-statement.md)
