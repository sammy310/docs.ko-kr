---
title: '방법: 문자열 안의 문자에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352466"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="f7c99-102">방법: Visual Basic에서 문자열 안의 문자에 액세스</span><span class="sxs-lookup"><span data-stu-id="f7c99-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="f7c99-103">이 예제에서는 <xref:System.String.Chars%2A> 속성을 사용 하 여 문자열의 지정 된 위치에 있는 문자에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7c99-104">예제</span><span class="sxs-lookup"><span data-stu-id="f7c99-104">Example</span></span>  
 <span data-ttu-id="f7c99-105">문자열의 문자에 대 한 데이터와 문자열 내에서 해당 문자의 위치에 대 한 데이터를 포함 하는 것이 유용한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="f7c99-106">문자열을 문자 배열 (`Char` 인스턴스)로 간주할 수 있습니다. <xref:System.String.Chars%2A> 속성을 통해 해당 문자의 인덱스를 참조 하 여 특정 문자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="f7c99-107"><xref:System.String.Chars%2A> 속성의 `index` 매개 변수는 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f7c99-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f7c99-108">Robust Programming</span></span>  
 <span data-ttu-id="f7c99-109"><xref:System.String.Chars%2A> 속성은 지정 된 위치에 있는 문자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="f7c99-110">그러나 일부 유니코드 문자는 둘 이상의 문자로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="f7c99-111">유니코드 문자로 작업 하는 방법에 대 한 자세한 내용은 [방법: 문자열을 문자 배열로 변환](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7c99-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="f7c99-112"><xref:System.String.Chars%2A> 속성은 `index` 매개 변수가 문자열의 길이 보다 크거나 같거나 0 보다 작은 경우 <xref:System.IndexOutOfRangeException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7c99-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c99-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7c99-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="f7c99-114">방법: 문자열을 문자 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="f7c99-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="f7c99-115">Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환</span><span class="sxs-lookup"><span data-stu-id="f7c99-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="f7c99-116">문자열</span><span class="sxs-lookup"><span data-stu-id="f7c99-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
