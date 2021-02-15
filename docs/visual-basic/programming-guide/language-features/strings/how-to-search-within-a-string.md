---
description: '방법에 대 한 자세한 정보: 방법: 문자열 내에서 검색 (Visual Basic)'
title: '방법: 문자열 내에서 검색'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: dab9faf91eef2e6d845805693227e1a6735ec796
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429730"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="af354-103">방법: 문자열 내에서 검색 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af354-103">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="af354-104">이 문서에서는 Visual Basic 문자열 내에서 검색 하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af354-104">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="af354-105">예</span><span class="sxs-lookup"><span data-stu-id="af354-105">Example</span></span>

<span data-ttu-id="af354-106">이 예제에서는 <xref:System.String.IndexOf%2A> 개체의 메서드를 호출 <xref:System.String> 하 여 첫 번째 부분 문자열의 인덱스를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="af354-106">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="af354-107">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="af354-107">Robust programming</span></span>

<span data-ttu-id="af354-108"><xref:System.String.IndexOf%2A>메서드는 맨 처음 발견 되는 부분 문자열의 첫 번째 문자 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af354-108">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="af354-109">인덱스는 0부터 시작 하며,이는 문자열의 첫 번째 문자에 인덱스가 0 인 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="af354-109">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="af354-110">에서 <xref:System.String.IndexOf%2A> 부분 문자열을 찾지 못하면-1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af354-110">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="af354-111"><xref:System.String.IndexOf%2A>메서드는 대/소문자를 구분 하며 현재 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af354-111">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="af354-112">최적의 오류 제어를 위해 `Try` Try ...의 블록에 문자열 검색을 포함 하는 것이 좋습니다. [ Catch ... Finally 문](../../../language-reference/statements/try-catch-finally-statement.md) 생성</span><span class="sxs-lookup"><span data-stu-id="af354-112">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="af354-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af354-113">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="af354-114">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="af354-114">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="af354-115">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="af354-115">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="af354-116">문자열</span><span class="sxs-lookup"><span data-stu-id="af354-116">Strings</span></span>](index.md)
