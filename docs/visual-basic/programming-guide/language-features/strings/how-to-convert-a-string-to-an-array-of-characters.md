---
description: '자세한 정보: 방법: 문자열을 Visual Basic의 문자 배열로 변환'
title: '방법: 문자열을 문자 배열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: f85b0801cf013e207eacd70a256a3ed0a8dc7887
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476152"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="392d3-103">방법: Visual Basic에서 문자열을 문자 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="392d3-103">How to: Convert a String to an Array of Characters in Visual Basic</span></span>

<span data-ttu-id="392d3-104">문자열의 문자에 대 한 데이터를 포함 하는 것이 유용한 경우도 있습니다. 예를 들어 문자열을 구문 분석 하는 경우에는 문자열 내에서 해당 문자 위치에 대 한 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="392d3-104">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="392d3-105">이 예제에서는 문자열의 메서드를 호출 하 여 문자열의 문자 배열을 가져오는 방법을 보여 줍니다 <xref:System.String.ToCharArray%2A> .</span><span class="sxs-lookup"><span data-stu-id="392d3-105">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="392d3-106">예</span><span class="sxs-lookup"><span data-stu-id="392d3-106">Example</span></span>  

 <span data-ttu-id="392d3-107">이 예제에서는 문자열을 배열로 분할 하는 방법 `Char` 및 문자열을 `String` 유니코드 텍스트 문자 배열로 분할 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="392d3-107">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="392d3-108">이러한 구분의 이유는 유니코드 텍스트 문자를 두 개 이상의 `Char` 문자 (예: 서로게이트 쌍 또는 결합 문자 시퀀스)로 구성할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="392d3-108">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="392d3-109">자세한 내용은 <xref:System.Globalization.TextElementEnumerator> 및 [유니코드 표준](https://www.unicode.org/standard/standard.html)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="392d3-109">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="392d3-110">예</span><span class="sxs-lookup"><span data-stu-id="392d3-110">Example</span></span>  

 <span data-ttu-id="392d3-111">문자열을 유니코드 텍스트 문자로 분할 하는 것이 더 어렵습니다. 문자열의 시각적 표현에 대 한 정보가 필요한 경우에는이 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="392d3-111">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="392d3-112">이 예제에서는 메서드를 사용 하 여 <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> 문자열을 구성 하는 유니코드 텍스트 문자에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="392d3-112">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="392d3-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="392d3-113">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="392d3-114">방법: 문자열에 있는 문자에 액세스</span><span class="sxs-lookup"><span data-stu-id="392d3-114">How to: Access Characters in Strings</span></span>](how-to-access-characters-in-strings.md)
- [<span data-ttu-id="392d3-115">Visual Basic에서 문자열 및 기타 데이터 형식 사이에 변환</span><span class="sxs-lookup"><span data-stu-id="392d3-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="392d3-116">문자열</span><span class="sxs-lookup"><span data-stu-id="392d3-116">Strings</span></span>](index.md)
