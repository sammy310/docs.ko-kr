---
title: REM 문
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: bdde4beae242c3175b02cd2af252babb850416f6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346724"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="d5485-102">REM 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5485-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="d5485-103">프로그램의 소스 코드에 설명 설명을 포함 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5485-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5485-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="d5485-105">요소</span><span class="sxs-lookup"><span data-stu-id="d5485-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="d5485-106">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d5485-106">Optional.</span></span> <span data-ttu-id="d5485-107">포함 하려는 주석의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-107">The text of any comment you want to include.</span></span> <span data-ttu-id="d5485-108">`REM` 키워드와 `comment`사이에 공백이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5485-109">주의</span><span class="sxs-lookup"><span data-stu-id="d5485-109">Remarks</span></span>  
 <span data-ttu-id="d5485-110">`REM` 문을 한 줄에 단독으로 넣거나 다른 문 다음의 줄에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="d5485-111">`REM` 문은 줄의 마지막 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="d5485-112">다른 문을 따르는 경우에는 `REM`를 해당 문에서 공백으로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="d5485-113">`REM`대신 작은따옴표 (`'`)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="d5485-114">이는 주석이 동일한 줄에서 다른 문을 팔 로우 하거나 한 줄에만 적용 되는지 여부에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d5485-115">`_`(줄 연속 시퀀스)를 사용 하 여 `REM` 문을 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="d5485-116">주석이 시작 되 면 컴파일러는 특수 한 의미에 대 한 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="d5485-117">여러 줄로 된 주석을 보려면 각 줄에서 다른 `REM` 문이나 주석 기호 (`'`)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5485-118">예제</span><span class="sxs-lookup"><span data-stu-id="d5485-118">Example</span></span>  
 <span data-ttu-id="d5485-119">다음 예에서는 프로그램에 설명 설명을 포함 하는 데 사용 되는 `REM` 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="d5485-120">또한 `REM`대신 작은따옴표 (`'`)를 사용 하는 대신 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5485-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d5485-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5485-121">See also</span></span>

- [<span data-ttu-id="d5485-122">코드 주석</span><span class="sxs-lookup"><span data-stu-id="d5485-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="d5485-123">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="d5485-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
