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
ms.openlocfilehash: 6161a9f7e589988882b5f76477bc069afd2b9b41
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871951"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="c4b72-102">REM 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4b72-102">REM Statement (Visual Basic)</span></span>

<span data-ttu-id="c4b72-103">프로그램의 소스 코드에 설명 설명을 포함 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b72-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4b72-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="c4b72-105">부분</span><span class="sxs-lookup"><span data-stu-id="c4b72-105">Parts</span></span>  

 `comment`  
 <span data-ttu-id="c4b72-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-106">Optional.</span></span> <span data-ttu-id="c4b72-107">포함 하려는 주석의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-107">The text of any comment you want to include.</span></span> <span data-ttu-id="c4b72-108">키워드와 사이에 공백이 필요 `REM` `comment` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4b72-109">설명</span><span class="sxs-lookup"><span data-stu-id="c4b72-109">Remarks</span></span>  

 <span data-ttu-id="c4b72-110">`REM`문을 한 줄에 단독으로 사용할 수도 있고 다른 문 다음에 오는 줄에 배치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="c4b72-111">`REM`문은 줄의 마지막 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="c4b72-112">다른 문 뒤에 오면은 `REM` 공백으로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="c4b72-113">대신 작은따옴표 ()를 사용할 수 있습니다 `'` `REM` .</span><span class="sxs-lookup"><span data-stu-id="c4b72-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="c4b72-114">이는 주석이 동일한 줄에서 다른 문을 팔 로우 하거나 한 줄에만 적용 되는지 여부에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4b72-115">`REM`줄 연속 시퀀스 ()를 사용 하 여 문을 계속할 수 없습니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="c4b72-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="c4b72-116">주석이 시작 되 면 컴파일러는 특수 한 의미에 대 한 문자를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="c4b72-117">여러 줄로 된 주석의 경우 `REM` 각 줄에 다른 문이나 주석 기호 ()를 사용 `'` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4b72-118">예제</span><span class="sxs-lookup"><span data-stu-id="c4b72-118">Example</span></span>  

 <span data-ttu-id="c4b72-119">다음 예에서는 `REM` 프로그램에 설명 설명을 포함 하는 데 사용 되는 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="c4b72-120">대신 작은따옴표 문자 ()를 사용 하는 대신 사용할 수도 `'` `REM` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4b72-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="c4b72-121">참조</span><span class="sxs-lookup"><span data-stu-id="c4b72-121">See also</span></span>

- [<span data-ttu-id="c4b72-122">코드 주석</span><span class="sxs-lookup"><span data-stu-id="c4b72-122">Comments in Code</span></span>](../../programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="c4b72-123">방법: 코드에서 명령문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="c4b72-123">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
