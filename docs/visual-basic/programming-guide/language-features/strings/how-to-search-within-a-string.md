---
title: '방법: 문자열 내에서 검색'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 655f746e4e496e1935afcd2a9f9fe36d9e3a2564
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348420"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="4c1b5-102">방법: 문자열 내에서 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c1b5-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="4c1b5-103">이 문서에서는 Visual Basic 문자열 내에서 검색 하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="4c1b5-104">예제</span><span class="sxs-lookup"><span data-stu-id="4c1b5-104">Example</span></span>

<span data-ttu-id="4c1b5-105">이 예제에서는 <xref:System.String> 개체의 <xref:System.String.IndexOf%2A> 메서드를 호출 하 여 첫 번째 부분 문자열의 인덱스를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="4c1b5-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4c1b5-106">Robust programming</span></span>

<span data-ttu-id="4c1b5-107"><xref:System.String.IndexOf%2A> 메서드는 맨 처음 발견 되는 부분 문자열의 첫 번째 문자 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="4c1b5-108">인덱스는 0부터 시작 하며,이는 문자열의 첫 번째 문자에 인덱스가 0 인 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="4c1b5-109"><xref:System.String.IndexOf%2A> 하위 문자열을 찾을 수 없는 경우-1이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="4c1b5-110"><xref:System.String.IndexOf%2A> 메서드는 대/소문자를 구분 하며 현재 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="4c1b5-111">최적의 오류 제어를 위해 Try ...의 `Try` 블록에 문자열 검색을 포함 하는 것이 좋습니다. [ Catch ... Finally 문](../../../language-reference/statements/try-catch-finally-statement.md) 생성</span><span class="sxs-lookup"><span data-stu-id="4c1b5-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c1b5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c1b5-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="4c1b5-113">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="4c1b5-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="4c1b5-114">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="4c1b5-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="4c1b5-115">문자열</span><span class="sxs-lookup"><span data-stu-id="4c1b5-115">Strings</span></span>](index.md)
