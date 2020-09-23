---
title: 0부터 시작하는 문자열 액세스 및 1부터 시작하는 문자열 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 91d3fb9d7bfdf3d5af27fc6499583640946a802f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072290"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="7905b-102">Visual Basic에서 0부터 시작하는 문자열 액세스와 1부터 시작하는 문자열 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="7905b-102">Zero-based vs. One-based String Access in Visual Basic</span></span>

<span data-ttu-id="7905b-103">이 항목에서는 Visual Basic 및 .NET Framework에서 문자열의 문자에 대 한 액세스를 제공 하는 방법을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="7905b-104">.NET Framework는 항상 문자열의 문자에 대 한 0부터 시작 하는 액세스를 제공 하는 반면 Visual Basic는 함수에 따라 0부터 시작 하는 액세스와 1부터 시작 하는 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="7905b-105">1부터</span><span class="sxs-lookup"><span data-stu-id="7905b-105">One-Based</span></span>  

 <span data-ttu-id="7905b-106">1부터 Visual Basic 함수를 사용 하는 방법에 대 한 예는 함수를 참조 `Mid` 하세요.</span><span class="sxs-lookup"><span data-stu-id="7905b-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="7905b-107">위치 1부터 시작 하 여 부분 문자열이 시작 되는 문자 위치를 나타내는 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="7905b-108">.NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 위치 0부터 시작 하 여 부분 문자열이 시작 될 문자열의 문자 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="7905b-109">따라서 "ABCDE...Z" 문자열을 사용 하는 경우 개별 문자는 함수와 함께 사용 하기 위해 1, 2, 3, 4, 5로 번호가 매겨집니다 `Mid` . 하지만 메서드와 함께 사용할 경우에는 0, 1, 2, 3, 4입니다 <xref:System.String.Substring%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7905b-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="7905b-110">0부터 시작</span><span class="sxs-lookup"><span data-stu-id="7905b-110">Zero-Based</span></span>  

 <span data-ttu-id="7905b-111">0부터 시작 하는 Visual Basic 함수의 예는 함수를 참조 `Split` 하세요.</span><span class="sxs-lookup"><span data-stu-id="7905b-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="7905b-112">문자열을 분할 하 고 부분 문자열을 포함 하는 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7905b-113">또한 .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드는 문자열을 분할 하 고 부분 문자열을 포함 하는 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7905b-114">`Split`함수 및 메서드는 <xref:System.String.Split%2A> .NET Framework 배열을 반환 하기 때문에 0부터 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7905b-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7905b-115">참조</span><span class="sxs-lookup"><span data-stu-id="7905b-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="7905b-116">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="7905b-116">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
