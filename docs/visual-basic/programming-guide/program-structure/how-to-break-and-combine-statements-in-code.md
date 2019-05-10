---
title: '방법: (Visual Basic) 코드에서 문 분리 및 결합'
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
ms.openlocfilehash: d3656b924ebaca67c90dc602701c4cef9ce088b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648786"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="d612a-102">방법: (Visual Basic) 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="d612a-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="d612a-103">코드를 작성할 때 코드 편집기에서 가로 스크롤을 볼 수 있는 긴 문을 시간에 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="d612a-104">방식에 영향을 주지 않지만 코드 실행, 하기 어렵습니다에 누구나 모니터에 표시 된 대로 코드를 읽는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="d612a-105">이러한 경우 긴 문은 여러 줄으로 분리를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="d612a-106">단일 문에 여러 줄으로 중단</span><span class="sxs-lookup"><span data-stu-id="d612a-106">To break a single statement into multiple lines</span></span>  
  
- <span data-ttu-id="d612a-107">밑줄 줄 연속 문자를 사용 하 여 (`_`), 줄을 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="d612a-108">밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자(캐리지 리턴)가 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d612a-109">경우에 따라 줄 연속 문자를 생략 하면 Visual Basic 컴파일러는 암시적으로 문을 계속 코드의 다음 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="d612a-110">"암시적 줄 연속 문자" 참조 목록은 구문 요소는 줄 연속 문자를 생략할 수 있습니다 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="d612a-111">다음 예제에서는 문의 마지막 줄을 제외한 모든 종료 줄 연속 문자를 사용 하 여 네 줄으로 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="d612a-112">이 시퀀스를 사용 하면 온라인 및 때 인쇄 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="d612a-113">줄 연속 문자에는 줄에서 마지막 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="d612a-114">같은 줄에 다른 요소와 따를 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="d612a-115">줄 연속 문자를 사용할 수 있는 수에 대 한 몇 가지 제한 사항이 존재 예를 들어 인수 이름 중 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="d612a-116">줄 연속 문자를 사용 하 여 인수 목록이 분리할 수 있지만 각 인수 이름은 그대로 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="d612a-117">주석 줄 연속 문자를 사용 하 여 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="d612a-118">컴파일러 특별 한 의미에 대 한 설명의 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="d612a-119">여러 줄 주석의 경우 반복 주석 기호 (`'`) 각 줄에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="d612a-120">하지만 각 문을 별도 줄에 배치 하는 것이 좋지만, Visual Basic 할 수도 있습니다 같은 줄에 여러 문 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="d612a-121">같은 줄에 여러 문 배치</span><span class="sxs-lookup"><span data-stu-id="d612a-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="d612a-122">문이 콜론으로 구분 (`:`) 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d612a-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="d612a-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="d612a-123">See also</span></span>

- [<span data-ttu-id="d612a-124">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="d612a-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="d612a-125">문(C++)</span><span class="sxs-lookup"><span data-stu-id="d612a-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
