---
title: '방법: 레이블 문 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050439"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="93f7f-102">방법: 레이블 문 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93f7f-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="93f7f-103">문 블록은 콜론으로 구분 하는 코드 줄으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="93f7f-104">코드를 식별 하는 문자열 또는 정수 앞에 줄 수 있다고 *레이블이 지정 된*합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="93f7f-105">문 레이블은 사용에 대 한 문을 사용 하 여 같은 식별 하는 코드 줄을 표시 하 되 `On Error Goto`합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="93f7f-106">레이블은 유효한 Visual Basic 식별자 중 하나를 수 있습니다-프로그래밍 요소를 식별 하는 것과 같은-또는 정수 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="93f7f-107">레이블을 소스 코드 줄의 시작 부분에 표시 되 고 같은 줄에서 문에 의해 뒤 여부에 관계 없이 콜론으로와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="93f7f-108">컴파일러는 줄의 시작 부분에 이미 정의 된 식별자 일치 하는지 여부를 확인 하 여 레이블을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="93f7f-109">표시 되지 않는 경우 컴파일러는 레이블 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="93f7f-110">레이블을 자체 선언 공간 있고 다른 식별자를 방해 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="93f7f-111">레이블의 범위는 메서드의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="93f7f-112">레이블 선언 모호한 경우에 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93f7f-113">레이블은 메서드 내에서 실행 가능 문을 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="93f7f-114">코드 줄 레이블을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="93f7f-114">To label a line of code</span></span>  
  
- <span data-ttu-id="93f7f-115">소스 코드 줄의 시작 부분에 콜론 뒤에 식별자를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f7f-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="93f7f-116">예를 들어, 다음 코드 줄은 레이블이 지정 된 `Jump` 고 `120`, 각각.</span><span class="sxs-lookup"><span data-stu-id="93f7f-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a><span data-ttu-id="93f7f-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="93f7f-117">See also</span></span>

- [<span data-ttu-id="93f7f-118">문(C++)</span><span class="sxs-lookup"><span data-stu-id="93f7f-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="93f7f-119">선언 요소 이름</span><span class="sxs-lookup"><span data-stu-id="93f7f-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="93f7f-120">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="93f7f-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
