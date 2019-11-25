---
title: Mid 문
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
ms.openlocfilehash: eeef4c13743b75a3d5e61ac46afb94d9ea105b7a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348035"
---
# <a name="mid-statement"></a><span data-ttu-id="27212-102">Mid 문</span><span class="sxs-lookup"><span data-stu-id="27212-102">Mid Statement</span></span>
<span data-ttu-id="27212-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span><span class="sxs-lookup"><span data-stu-id="27212-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27212-104">구문</span><span class="sxs-lookup"><span data-stu-id="27212-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="27212-105">요소</span><span class="sxs-lookup"><span data-stu-id="27212-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="27212-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="27212-106">Required.</span></span> <span data-ttu-id="27212-107">Name of the `String` variable to modify.</span><span class="sxs-lookup"><span data-stu-id="27212-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="27212-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="27212-108">Required.</span></span> <span data-ttu-id="27212-109">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="27212-109">`Integer` expression.</span></span> <span data-ttu-id="27212-110">Character position in `Target` where the replacement of text begins.</span><span class="sxs-lookup"><span data-stu-id="27212-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="27212-111">`Start` uses a one-based index.</span><span class="sxs-lookup"><span data-stu-id="27212-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="27212-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="27212-112">Optional.</span></span> <span data-ttu-id="27212-113">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="27212-113">`Integer` expression.</span></span> <span data-ttu-id="27212-114">Number of characters to replace.</span><span class="sxs-lookup"><span data-stu-id="27212-114">Number of characters to replace.</span></span> <span data-ttu-id="27212-115">If omitted, all of `String` is used.</span><span class="sxs-lookup"><span data-stu-id="27212-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="27212-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="27212-116">Required.</span></span> <span data-ttu-id="27212-117">`String` expression that replaces part of `Target`.</span><span class="sxs-lookup"><span data-stu-id="27212-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="27212-118">예외</span><span class="sxs-lookup"><span data-stu-id="27212-118">Exceptions</span></span>  
  
|<span data-ttu-id="27212-119">예외 형식</span><span class="sxs-lookup"><span data-stu-id="27212-119">Exception type</span></span>|<span data-ttu-id="27212-120">조건</span><span class="sxs-lookup"><span data-stu-id="27212-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="27212-121">`Start` <= 0 or `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="27212-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27212-122">주의</span><span class="sxs-lookup"><span data-stu-id="27212-122">Remarks</span></span>  
 <span data-ttu-id="27212-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span><span class="sxs-lookup"><span data-stu-id="27212-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="27212-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span><span class="sxs-lookup"><span data-stu-id="27212-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="27212-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span><span class="sxs-lookup"><span data-stu-id="27212-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="27212-126">자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27212-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27212-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span><span class="sxs-lookup"><span data-stu-id="27212-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="27212-128">더블 바이트 문자 집합 (DBCS) 애플리케이션의 문자열을 변환에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27212-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="27212-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span><span class="sxs-lookup"><span data-stu-id="27212-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27212-130">예제</span><span class="sxs-lookup"><span data-stu-id="27212-130">Example</span></span>  
 <span data-ttu-id="27212-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span><span class="sxs-lookup"><span data-stu-id="27212-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="27212-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27212-132">Requirements</span></span>  
 <span data-ttu-id="27212-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="27212-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="27212-134">**Module:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="27212-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="27212-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="27212-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27212-136">참조</span><span class="sxs-lookup"><span data-stu-id="27212-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="27212-137">문자열</span><span class="sxs-lookup"><span data-stu-id="27212-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="27212-138">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="27212-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
