---
title: '방법: Visual Basic에서 문자 배열에 문자열 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 921d7ad62545d3a29870aee6c6b354fdadeb0500
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938361"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="9b8bf-102">방법: Visual Basic에서 문자 배열에 문자열 변환</span><span class="sxs-lookup"><span data-stu-id="9b8bf-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="9b8bf-103">경우에 따라 문자열을 구문 분석 하는 경우 처럼 문자열 내에서 해당 문자의 위치 및 문자열의 문자에 대 한 데이터가 있어야 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8bf-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="9b8bf-104">문자열을 호출 하 여 문자열에서 문자의 배열을 가져올 수는 방법을 보여 주는이 예제 <xref:System.String.ToCharArray%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b8bf-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b8bf-105">예제</span><span class="sxs-lookup"><span data-stu-id="9b8bf-105">Example</span></span>  
 <span data-ttu-id="9b8bf-106">이 예제에서는 문자열을 분할 하는 방법에 설명를 `Char` 배열 및 문자열을 분할 하는 방법을 `String` 해당 유니코드 텍스트 문자의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8bf-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="9b8bf-107">이러한 차이 대 한 이유는 두 개 이상의 유니코드 텍스트 문자를 구성할 수 있습니다 `Char` 문자 (서로게이트 쌍 등을 결합 문자 시퀀스).</span><span class="sxs-lookup"><span data-stu-id="9b8bf-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="9b8bf-108">자세한 내용은 <xref:System.Globalization.TextElementEnumerator> 하 고 [유니코드 표준](https://www.unicode.org/standard/standard.html)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8bf-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="9b8bf-109">예제</span><span class="sxs-lookup"><span data-stu-id="9b8bf-109">Example</span></span>  
 <span data-ttu-id="9b8bf-110">유니코드 텍스트 문자를 문자열로 분할할 하기가 더 어렵습니다이 하지만 문자열의 시각적 표현에 대 한 정보가 필요한 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8bf-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="9b8bf-111">이 예제에서는 <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> 메서드 문자열을 구성 하는 유니코드 텍스트 문자에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8bf-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="9b8bf-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b8bf-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="9b8bf-113">방법: 문자열의 문자 액세스</span><span class="sxs-lookup"><span data-stu-id="9b8bf-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="9b8bf-114">Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환</span><span class="sxs-lookup"><span data-stu-id="9b8bf-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="9b8bf-115">문자열</span><span class="sxs-lookup"><span data-stu-id="9b8bf-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
