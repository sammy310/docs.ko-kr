---
title: '방법: Label 문'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 8f04d592c51b6a0630bfe623fd3574555aef9ff8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403215"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="7a71e-102">방법: Label 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a71e-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="7a71e-103">문 블록은 콜론으로 구분 된 코드 줄로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="7a71e-104">식별 문자열이 나 정수로 시작 하는 코드 줄에는 *레이블이 지정*된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="7a71e-105">문 레이블은와 같은 문에서 사용할 수 있도록 코드 줄을 표시 하는 데 사용 됩니다 `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="7a71e-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="7a71e-106">레이블은 프로그래밍 요소를 식별 하는 식별자 (예: 올바른 Visual Basic 식별자 또는 정수 리터럴) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="7a71e-107">레이블은 소스 코드 줄의 시작 부분에 표시 되어야 하며, 뒤에 동일한 줄에 문이 있는지 여부에 관계 없이 콜론이와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="7a71e-108">컴파일러는 줄의 시작 부분이 이미 정의 된 식별자와 일치 하는지 여부를 확인 하 여 레이블을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="7a71e-109">그렇지 않은 경우 컴파일러는 레이블로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="7a71e-110">레이블은 고유한 선언 공간을 가지 며 다른 식별자를 방해 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="7a71e-111">레이블의 범위는 메서드의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="7a71e-112">모호한 상황에서는 레이블 선언이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="7a71e-113">레이블은 메서드 내의 실행 가능한 문에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="7a71e-114">코드 줄에 레이블을 만들려면</span><span class="sxs-lookup"><span data-stu-id="7a71e-114">To label a line of code</span></span>

<span data-ttu-id="7a71e-115">소스 코드 줄의 시작 부분에서 식별자 뒤에 콜론을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a71e-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="7a71e-116">예를 들어 다음 코드 줄은 각각 및로 레이블이 지정 됩니다 `Jump` `120` .</span><span class="sxs-lookup"><span data-stu-id="7a71e-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="7a71e-117">참조</span><span class="sxs-lookup"><span data-stu-id="7a71e-117">See also</span></span>

- [<span data-ttu-id="7a71e-118">문</span><span class="sxs-lookup"><span data-stu-id="7a71e-118">Statements</span></span>](../language-features/statements.md)
- [<span data-ttu-id="7a71e-119">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="7a71e-119">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="7a71e-120">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="7a71e-120">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
