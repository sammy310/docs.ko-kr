---
description: '자세히 알아보기: Mid 문'
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
ms.openlocfilehash: 29cf933cb38fc6ef831570d0940b481abf9cfecf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768885"
---
# <a name="mid-statement"></a><span data-ttu-id="70ed8-103">Mid 문</span><span class="sxs-lookup"><span data-stu-id="70ed8-103">Mid Statement</span></span>

<span data-ttu-id="70ed8-104">변수의 지정 된 문자 수를 `String` 다른 문자열의 문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-104">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70ed8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="70ed8-105">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="70ed8-106">부분</span><span class="sxs-lookup"><span data-stu-id="70ed8-106">Parts</span></span>  

 `Target`  
 <span data-ttu-id="70ed8-107">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-107">Required.</span></span> <span data-ttu-id="70ed8-108">`String`수정할 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-108">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="70ed8-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="70ed8-109">Required.</span></span> <span data-ttu-id="70ed8-110">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-110">`Integer` expression.</span></span> <span data-ttu-id="70ed8-111">텍스트 바꾸기가 시작 되는의 문자 위치 `Target` 입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-111">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="70ed8-112">`Start` 는 1부터 사용 하는 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-112">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="70ed8-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-113">Optional.</span></span> <span data-ttu-id="70ed8-114">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-114">`Integer` expression.</span></span> <span data-ttu-id="70ed8-115">바꿀 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-115">Number of characters to replace.</span></span> <span data-ttu-id="70ed8-116">생략 하면 `String` 가 모두 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-116">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="70ed8-117">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-117">Required.</span></span> <span data-ttu-id="70ed8-118">`String` 의 일부를 바꾸는 식입니다 `Target` .</span><span class="sxs-lookup"><span data-stu-id="70ed8-118">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="70ed8-119">예외</span><span class="sxs-lookup"><span data-stu-id="70ed8-119">Exceptions</span></span>  
  
|<span data-ttu-id="70ed8-120">예외 종류</span><span class="sxs-lookup"><span data-stu-id="70ed8-120">Exception type</span></span>|<span data-ttu-id="70ed8-121">조건</span><span class="sxs-lookup"><span data-stu-id="70ed8-121">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="70ed8-122">`Start` <= 0 또는 `Length` < 0입니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-122">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70ed8-123">설명</span><span class="sxs-lookup"><span data-stu-id="70ed8-123">Remarks</span></span>  

 <span data-ttu-id="70ed8-124">대체 되는 문자 수는 항상의 문자 수보다 작거나 같습니다 `Target` .</span><span class="sxs-lookup"><span data-stu-id="70ed8-124">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="70ed8-125">Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수와 `Mid` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-125">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="70ed8-126">이러한 요소는 모두 문자열에서 지정 된 수의 문자에서 작동 하지만 `Mid` 문이 문자를 대체 하는 동안 함수는 문자를 반환 합니다 `Mid` .</span><span class="sxs-lookup"><span data-stu-id="70ed8-126">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="70ed8-127">자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ed8-127">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70ed8-128">`MidB`이전 버전의 Visual Basic 문은 문자열이 아닌 바이트 단위로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-128">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="70ed8-129">더블 바이트 문자 집합 (DBCS) 애플리케이션의 문자열을 변환에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-129">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="70ed8-130">모든 Visual Basic 문자열은 유니코드로 되어 있으며 `MidB` 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-130">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70ed8-131">예제</span><span class="sxs-lookup"><span data-stu-id="70ed8-131">Example</span></span>  

 <span data-ttu-id="70ed8-132">이 예에서는 `Mid` 문을 사용 하 여 문자열 변수의 지정 된 문자 수를 다른 문자열의 문자로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="70ed8-132">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="70ed8-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70ed8-133">Requirements</span></span>  

 <span data-ttu-id="70ed8-134">**네임 스페이스:** [microsoft.visualbasic](../runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="70ed8-134">**Namespace:** [Microsoft.VisualBasic](../runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="70ed8-135">**모듈:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="70ed8-135">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="70ed8-136">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="70ed8-136">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ed8-137">참조</span><span class="sxs-lookup"><span data-stu-id="70ed8-137">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="70ed8-138">문자열</span><span class="sxs-lookup"><span data-stu-id="70ed8-138">Strings</span></span>](../../programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="70ed8-139">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="70ed8-139">Introduction to Strings in Visual Basic</span></span>](../../programming-guide/language-features/strings/introduction-to-strings.md)
