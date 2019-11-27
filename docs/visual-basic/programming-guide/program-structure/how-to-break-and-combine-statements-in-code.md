---
title: '방법: 코드에서 문 분리 및 결합'
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: f1a24c001cd20acc7663fb4cbe60e7e35a9c8fc3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347431"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="2ad57-102">방법: 코드에서 문 분리 및 결합(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ad57-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>

<span data-ttu-id="2ad57-103">코드를 작성할 때 코드 편집기에서 가로로 스크롤해야 하는 긴 문을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="2ad57-104">이는 코드가 실행 되는 방식에는 영향을 주지 않지만 사용자 또는 다른 사용자가 모니터에 표시 되는 코드를 읽을 수 있도록 하는 것이 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="2ad57-105">이 경우 단일 long 문을 여러 줄로 나누는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>

## <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="2ad57-106">단일 문을 여러 줄로 분할 하려면</span><span class="sxs-lookup"><span data-stu-id="2ad57-106">To break a single statement into multiple lines</span></span>

<span data-ttu-id="2ad57-107">줄 연속 문자를 사용 합니다 .이 문자는 줄을 나눌 지점에서 밑줄 (`_`)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="2ad57-108">밑줄 바로 앞에는 공백이 오고 바로 뒤에 줄 종결자 (캐리지 리턴)가와 야 합니다 (버전 16.0부터). 주석 뒤에 캐리지 리턴이와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return) or (starting with version 16.0) a comment followed by a carriage return.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2ad57-109">경우에 따라 줄 연속 문자를 생략 하는 경우 Visual Basic 컴파일러는 다음 코드 줄에서 문을 암시적으로 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="2ad57-110">줄 연속 문자를 생략할 수 있는 구문 요소 목록은 [문의](../../../visual-basic/programming-guide/language-features/statements.md)"암시적 줄 연속"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ad57-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>

  <span data-ttu-id="2ad57-111">다음 예제에서 문은 줄 연속 문자를 사용 하 여 마지막 줄을 제외한 4 개의 줄로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  <span data-ttu-id="2ad57-112">이 시퀀스를 사용 하면 온라인 및 인쇄 시 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>

  <span data-ttu-id="2ad57-113">줄 연속 문자는 줄에서 마지막 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="2ad57-114">동일한 줄에서 다른 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-114">You can't follow it with anything else on the same line.</span></span>

  <span data-ttu-id="2ad57-115">줄 연속 문자를 사용할 수 있는 위치에 대 한 몇 가지 제한이 있습니다. 예를 들어 인수 이름 중간에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="2ad57-116">줄 연속 문자를 사용 하 여 인수 목록을 나눌 수 있지만 인수의 개별 이름은 그대로 유지 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>

  <span data-ttu-id="2ad57-117">줄 연속 문자를 사용 하 여 주석을 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="2ad57-118">컴파일러는 특별 한 의미를 위해 주석의 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="2ad57-119">여러 줄로 된 주석을 보려면 각 줄에서 주석 기호 (`'`)를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>

 <span data-ttu-id="2ad57-120">각 문을 별도의 줄에 배치 하는 것이 좋습니다. Visual Basic을 사용 하면 여러 문을 같은 줄에 배치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>

## <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="2ad57-121">같은 줄에 여러 문을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="2ad57-121">To place multiple statements on the same line</span></span>

<span data-ttu-id="2ad57-122">다음 예제와 같이 문을 콜론 (`:`)으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ad57-122">Separate the statements with a colon (`:`), as in the following example:</span></span>

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a><span data-ttu-id="2ad57-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ad57-123">See also</span></span>

- [<span data-ttu-id="2ad57-124">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="2ad57-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="2ad57-125">문</span><span class="sxs-lookup"><span data-stu-id="2ad57-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
