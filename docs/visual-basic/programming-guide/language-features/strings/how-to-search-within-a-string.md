---
title: '방법: 검색 문자열 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: b690aa78a2cf07b0db5bdd28d7d71ed4a79fbf61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823300"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="3ae7a-102">방법: 검색 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ae7a-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="3ae7a-103">이 예제에서는 호출을 <xref:System.String.IndexOf%2A> 메서드는 <xref:System.String> 부분 문자열의 첫 번째 발생의 인덱스를 보고 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae7a-104">예제</span><span class="sxs-lookup"><span data-stu-id="3ae7a-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ae7a-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3ae7a-105">Compiling the Code</span></span>  
 <span data-ttu-id="3ae7a-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-106">This example requires:</span></span>  
  
-   <span data-ttu-id="3ae7a-107">`Imports` 문을 지정 하는 <xref:System> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="3ae7a-108">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3ae7a-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3ae7a-109">Robust Programming</span></span>  
 <span data-ttu-id="3ae7a-110"><xref:System.String.IndexOf%2A> 메서드 맨 처음 발견 되는 부분 문자열의 첫 번째 문자의 위치를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="3ae7a-111">인덱스는 0 기반, 즉, 문자열의 첫 번째 문자에는 인덱스가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="3ae7a-112">경우 <xref:System.String.IndexOf%2A> 부분 문자열을 찾지 못하면-1을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="3ae7a-113"><xref:System.String.IndexOf%2A> 메서드는 대/소문자 구분 및 현재 문화권을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="3ae7a-114">최적의 오류 컨트롤에 대 한 문자열 검색을 묶습니다 하려는 합니다 `Try` 블록을 [시도 하는 중... Catch 하는 중... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ae7a-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae7a-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="3ae7a-115">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="3ae7a-116">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="3ae7a-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="3ae7a-117">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="3ae7a-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="3ae7a-118">문자열</span><span class="sxs-lookup"><span data-stu-id="3ae7a-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
