---
description: '자세한 정보: 오류 형식 (Visual Basic)'
title: 오류 형식
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: cc4fce5e0ce77a4e402ba832fd6f4e36e6feed07
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423773"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="099fb-103">오류 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="099fb-103">Error Types (Visual Basic)</span></span>

<span data-ttu-id="099fb-104">Visual Basic 오류는 구문 오류, 런타임 오류 및 논리 오류의 세 가지 범주 중 하나에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-104">In Visual Basic, errors fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>

## <a name="syntax-errors"></a><span data-ttu-id="099fb-105">구문 오류</span><span class="sxs-lookup"><span data-stu-id="099fb-105">Syntax Errors</span></span>

 <span data-ttu-id="099fb-106">*구문 오류* 는 코드를 작성 하는 동안 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-106">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="099fb-107">Visual Studio를 사용 하는 경우 코드 **편집기** 창에서 코드 Visual Basic를 입력할 때 코드를 확인 하 고 단어의 철자를 잘못 입력 하거나 언어 요소를 잘못 사용 하는 등 실수를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-107">If you're using Visual Studio, Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="099fb-108">명령줄에서 컴파일하는 경우 Visual Basic 구문 오류에 대 한 정보와 함께 컴파일러 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-108">If you compile from the command line, Visual Basic displays a compiler error with information about the syntax error.</span></span> <span data-ttu-id="099fb-109">구문 오류는 가장 일반적인 오류 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-109">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="099fb-110">코딩 환경에서이를 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-110">You can fix them easily in the coding environment as soon as they occur.</span></span>

> [!NOTE]
> <span data-ttu-id="099fb-111">`Option Explicit`문은 구문 오류를 방지 하는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-111">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="099fb-112">응용 프로그램에서 사용 되는 모든 변수를 미리 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-112">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="099fb-113">따라서 코드에서 이러한 변수를 사용 하는 경우에는 모든 입력 오류를 즉시 catch 하 고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-113">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>

## <a name="run-time-errors"></a><span data-ttu-id="099fb-114">Run-Time 오류</span><span class="sxs-lookup"><span data-stu-id="099fb-114">Run-Time Errors</span></span>

 <span data-ttu-id="099fb-115">*런타임 오류* 는 코드를 컴파일하고 실행 한 후에만 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-115">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="099fb-116">여기에는 구문 오류가 없지만 실행 되지 않는 것 처럼 보이는 코드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-116">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="099fb-117">예를 들어 파일을 여는 코드 줄을 올바르게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-117">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="099fb-118">그러나 파일이 없으면 응용 프로그램에서 파일을 열 수 없으며 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-118">But if the file does not exist, the application cannot open the file, and it throws an exception.</span></span> <span data-ttu-id="099fb-119">잘못 된 코드를 다시 작성 하거나 [예외 처리](../../language-reference/statements/try-catch-finally-statement.md)를 사용 하 여 대부분의 런타임 오류를 수정한 다음 다시 컴파일하고 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-119">You can fix most run-time errors by rewriting the faulty code or by using [exception handling](../../language-reference/statements/try-catch-finally-statement.md), and then recompiling and rerunning it.</span></span>
  
## <a name="logic-errors"></a><span data-ttu-id="099fb-120">논리 오류</span><span class="sxs-lookup"><span data-stu-id="099fb-120">Logic Errors</span></span>

 <span data-ttu-id="099fb-121">*논리 오류* 는 응용 프로그램을 사용 하 고 있는 경우 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-121">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="099fb-122">대부분의 경우 개발자가 수행 하는 가장 일반적인 잘못 된 가정과 사용자 동작에 대 한 응답으로 원치 않거나 예기치 않은 결과가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-122">They are most often faulty assumptions made by the developer, or unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="099fb-123">예를 들어 잘못 입력 한 키는 메서드에 잘못 된 정보를 제공할 수 있으며, 그렇지 않은 경우에는 메서드에 올바른 값이 항상 제공 된다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-123">For example, a mistyped key might provide incorrect information to a method, or you may assume that a valid value is always supplied to a method when that is not the case.</span></span> <span data-ttu-id="099fb-124">[예외 처리](../../language-reference/statements/try-catch-finally-statement.md) 를 사용 하 여 논리 오류를 처리할 수 있지만 (예를 들어, 인수가 인지 여부를 테스트 하는 경우 `Nothing` <xref:System.ArgumentNullException> ), 일반적으로 논리 오류를 수정 하 고 응용 프로그램을 다시 컴파일하면 가장 일반적으로 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="099fb-124">Although logic errors can be handled by using [exception handling](../../language-reference/statements/try-catch-finally-statement.md) (for example, by testing whether an argument is `Nothing` and throwing an <xref:System.ArgumentNullException>), most commonly they should be addressed by correcting the error in logic and recompiling the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="099fb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="099fb-125">See also</span></span>

- [<span data-ttu-id="099fb-126">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="099fb-126">Try...Catch...Finally Statement</span></span>](../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="099fb-127">디버거 기본 사항</span><span class="sxs-lookup"><span data-stu-id="099fb-127">Debugger Basics</span></span>](/visualstudio/debugger/debugger-feature-tour)
