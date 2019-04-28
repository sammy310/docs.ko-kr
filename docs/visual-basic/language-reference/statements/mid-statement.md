---
title: Mid 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: df83fd527612af1a6a4b8131ffa2643ef0d1d7dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784238"
---
# <a name="mid-statement"></a><span data-ttu-id="9fbb2-102">Mid 문</span><span class="sxs-lookup"><span data-stu-id="9fbb2-102">Mid Statement</span></span>
<span data-ttu-id="9fbb2-103">지정 된 수의 문자 대체를 `String` 다른 문자열에서 문자를 사용 하 여 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbb2-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fbb2-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="9fbb2-105">요소</span><span class="sxs-lookup"><span data-stu-id="9fbb2-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="9fbb2-106">필수.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-106">Required.</span></span> <span data-ttu-id="9fbb2-107">이름을 합니다 `String` 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="9fbb2-108">필수.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-108">Required.</span></span> <span data-ttu-id="9fbb2-109">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-109">`Integer` expression.</span></span> <span data-ttu-id="9fbb2-110">문자 위치 `Target` 바꿀 텍스트가 시작 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="9fbb2-111">`Start` 1부터 시작 하는 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="9fbb2-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-112">Optional.</span></span> <span data-ttu-id="9fbb2-113">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-113">`Integer` expression.</span></span> <span data-ttu-id="9fbb2-114">교체할 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-114">Number of characters to replace.</span></span> <span data-ttu-id="9fbb2-115">생략 하면 모든 `String` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="9fbb2-116">필수.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-116">Required.</span></span> <span data-ttu-id="9fbb2-117">`String` 식의 일부를 대체 하는 `Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="9fbb2-118">예외</span><span class="sxs-lookup"><span data-stu-id="9fbb2-118">Exceptions</span></span>  
  
|<span data-ttu-id="9fbb2-119">예외 형식</span><span class="sxs-lookup"><span data-stu-id="9fbb2-119">Exception type</span></span>|<span data-ttu-id="9fbb2-120">조건</span><span class="sxs-lookup"><span data-stu-id="9fbb2-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="9fbb2-121">`Start` < = 0 또는 `Length` < 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fbb2-122">설명</span><span class="sxs-lookup"><span data-stu-id="9fbb2-122">Remarks</span></span>  
 <span data-ttu-id="9fbb2-123">대체 문자 수는 항상의 문자 수가 작거나 `Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="9fbb2-124">Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수 및 `Mid` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="9fbb2-125">이러한 요소는 모두 문자열에서 문자의 지정된 된 수에 작동 하지만 `Mid` 해당 문자를 반환 하는 함수는 `Mid` 문은 문자를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="9fbb2-126">자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fbb2-127">`MidB` 이전 버전의 Visual Basic의 문 문자가 아닌 바이트를의 부분 문자열을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="9fbb2-128">더블 바이트 문자 집합 (DBCS) 응용 프로그램의 문자열을 변환에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="9fbb2-129">모든 Visual Basic 문자열은 유니코드, 및 `MidB` 는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fbb2-130">예제</span><span class="sxs-lookup"><span data-stu-id="9fbb2-130">Example</span></span>  
 <span data-ttu-id="9fbb2-131">이 예제에서는 `Mid` 문을 다른 문자열에 지정 된 개수의 문자열 변수에 문자를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9fbb2-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="9fbb2-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fbb2-132">Requirements</span></span>  
 <span data-ttu-id="9fbb2-133">**네임스페이스:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="9fbb2-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="9fbb2-134">**모듈:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="9fbb2-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="9fbb2-135">**어셈블리:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fbb2-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbb2-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fbb2-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="9fbb2-137">문자열</span><span class="sxs-lookup"><span data-stu-id="9fbb2-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="9fbb2-138">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="9fbb2-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
