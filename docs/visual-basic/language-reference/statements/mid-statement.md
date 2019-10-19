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
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581483"
---
# <a name="mid-statement"></a><span data-ttu-id="85846-102">Mid 문</span><span class="sxs-lookup"><span data-stu-id="85846-102">Mid Statement</span></span>
<span data-ttu-id="85846-103">@No__t_0 변수의 지정 된 문자 수를 다른 문자열의 문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85846-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85846-104">구문</span><span class="sxs-lookup"><span data-stu-id="85846-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="85846-105">요소</span><span class="sxs-lookup"><span data-stu-id="85846-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="85846-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="85846-106">Required.</span></span> <span data-ttu-id="85846-107">수정할 `String` 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="85846-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="85846-108">Required.</span></span> <span data-ttu-id="85846-109">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-109">`Integer` expression.</span></span> <span data-ttu-id="85846-110">텍스트 바꾸기가 시작 되는 `Target`의 문자 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="85846-111">`Start`는 1부터 사용 하는 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85846-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="85846-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="85846-112">Optional.</span></span> <span data-ttu-id="85846-113">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-113">`Integer` expression.</span></span> <span data-ttu-id="85846-114">바꿀 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-114">Number of characters to replace.</span></span> <span data-ttu-id="85846-115">생략 하면 모든 `String` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85846-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="85846-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="85846-116">Required.</span></span> <span data-ttu-id="85846-117">`Target`의 일부를 대체 하는 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="85846-118">예외</span><span class="sxs-lookup"><span data-stu-id="85846-118">Exceptions</span></span>  
  
|<span data-ttu-id="85846-119">예외 형식</span><span class="sxs-lookup"><span data-stu-id="85846-119">Exception type</span></span>|<span data-ttu-id="85846-120">조건</span><span class="sxs-lookup"><span data-stu-id="85846-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="85846-121">`Start` < = 0 또는 `Length` < 0입니다.</span><span class="sxs-lookup"><span data-stu-id="85846-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85846-122">주의</span><span class="sxs-lookup"><span data-stu-id="85846-122">Remarks</span></span>  
 <span data-ttu-id="85846-123">대체 되는 문자 수는 항상 `Target`의 문자 수보다 작거나 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85846-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="85846-124">Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수와 `Mid` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85846-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="85846-125">이러한 요소는 모두 문자열에서 지정 된 수의 문자에서 작동 하지만 `Mid` 문이 문자를 대체 하는 동안 `Mid` 함수는 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="85846-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="85846-126">자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="85846-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85846-127">이전 버전의 Visual Basic `MidB` 문은 문자열이 아닌 바이트 단위로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="85846-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="85846-128">더블 바이트 문자 집합 (DBCS) 애플리케이션의 문자열을 변환에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85846-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="85846-129">모든 Visual Basic 문자열은 유니코드 이며 `MidB`는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85846-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85846-130">예제</span><span class="sxs-lookup"><span data-stu-id="85846-130">Example</span></span>  
 <span data-ttu-id="85846-131">이 예에서는 `Mid` 문을 사용 하 여 문자열 변수의 지정 된 문자 수를 다른 문자열의 문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="85846-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="85846-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85846-132">Requirements</span></span>  
 <span data-ttu-id="85846-133">**네임 스페이스:** [microsoft.visualbasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="85846-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="85846-134">**모듈:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="85846-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="85846-135">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.visualbasic)</span><span class="sxs-lookup"><span data-stu-id="85846-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85846-136">참조</span><span class="sxs-lookup"><span data-stu-id="85846-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="85846-137">문자열</span><span class="sxs-lookup"><span data-stu-id="85846-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="85846-138">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="85846-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
