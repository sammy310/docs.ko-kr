---
title: '방법: 문자열 내에서 검색-Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: fe9e50dc5458fdf8546094e5f41c2f001f1d2791
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700070"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="a1322-102">방법: 문자열 내에서 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1322-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="a1322-103">이 문서에서는 Visual Basic 문자열 내에서 검색 하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1322-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="a1322-104">예제</span><span class="sxs-lookup"><span data-stu-id="a1322-104">Example</span></span>

<span data-ttu-id="a1322-105">이 예에서는 <xref:System.String> 개체의 <xref:System.String.IndexOf%2A> 메서드를 호출 하 여 첫 번째 부분 문자열의 인덱스를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1322-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="a1322-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a1322-106">Robust programming</span></span>

<span data-ttu-id="a1322-107">@No__t-0 메서드는 맨 처음 발견 되는 부분 문자열의 첫 번째 문자 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1322-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="a1322-108">인덱스는 0부터 시작 하며,이는 문자열의 첫 번째 문자에 인덱스가 0 인 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1322-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="a1322-109">@No__t-0은 부분 문자열을 찾지 못하면-1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1322-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="a1322-110">@No__t-0 메서드는 대/소문자를 구분 하며 현재 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1322-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="a1322-111">최적의 오류 제어를 위해 Try ...의 `Try` 블록에 문자열 검색을 포함 하는 것이 좋습니다. [ Catch ... Finally 문](../../../language-reference/statements/try-catch-finally-statement.md) 생성</span><span class="sxs-lookup"><span data-stu-id="a1322-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1322-112">참조</span><span class="sxs-lookup"><span data-stu-id="a1322-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="a1322-113">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="a1322-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="a1322-114">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="a1322-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="a1322-115">문자열</span><span class="sxs-lookup"><span data-stu-id="a1322-115">Strings</span></span>](index.md)
