---
description: '자세한 정보: 방법: Label 문 (Visual Basic)'
title: '방법: Label 문'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 4efb320dad7d52f6e9b94f6e6f81730f94b5966b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433254"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="fc391-103">방법: Label 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc391-103">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="fc391-104">문 블록은 콜론으로 구분 된 코드 줄로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-104">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="fc391-105">식별 문자열이 나 정수로 시작 하는 코드 줄에는 *레이블이 지정* 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-105">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="fc391-106">문 레이블은와 같은 문에서 사용할 수 있도록 코드 줄을 표시 하는 데 사용 됩니다 `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="fc391-106">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="fc391-107">레이블은 프로그래밍 요소를 식별 하는 식별자 (예: 올바른 Visual Basic 식별자 또는 정수 리터럴) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-107">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="fc391-108">레이블은 소스 코드 줄의 시작 부분에 표시 되어야 하며, 뒤에 동일한 줄에 문이 있는지 여부에 관계 없이 콜론이와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-108">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="fc391-109">컴파일러는 줄의 시작 부분이 이미 정의 된 식별자와 일치 하는지 여부를 확인 하 여 레이블을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-109">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="fc391-110">그렇지 않은 경우 컴파일러는 레이블로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-110">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="fc391-111">레이블은 고유한 선언 공간을 가지 며 다른 식별자를 방해 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-111">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="fc391-112">레이블의 범위는 메서드의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-112">A label's scope is the body of the method.</span></span> <span data-ttu-id="fc391-113">모호한 상황에서는 레이블 선언이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-113">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="fc391-114">레이블은 메서드 내의 실행 가능한 문에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-114">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="fc391-115">코드 줄에 레이블을 만들려면</span><span class="sxs-lookup"><span data-stu-id="fc391-115">To label a line of code</span></span>

<span data-ttu-id="fc391-116">소스 코드 줄의 시작 부분에서 식별자 뒤에 콜론을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc391-116">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="fc391-117">예를 들어 다음 코드 줄은 각각 및로 레이블이 지정 됩니다 `Jump` `120` .</span><span class="sxs-lookup"><span data-stu-id="fc391-117">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="fc391-118">참조</span><span class="sxs-lookup"><span data-stu-id="fc391-118">See also</span></span>

- [<span data-ttu-id="fc391-119">문</span><span class="sxs-lookup"><span data-stu-id="fc391-119">Statements</span></span>](../language-features/statements.md)
- [<span data-ttu-id="fc391-120">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="fc391-120">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="fc391-121">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="fc391-121">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
