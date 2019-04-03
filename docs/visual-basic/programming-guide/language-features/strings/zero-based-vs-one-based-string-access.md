---
title: 0부터 시작하는 문자열 액세스 및 Visual Basic의 1부터 시작 하는 문자열 액세스 비교
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a6ceb10d4a3cb9463551d8c85375ddbbb607ffdc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830333"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="657c6-102">0부터 시작하는 문자열 액세스 및 Visual Basic의 1부터 시작 하는 문자열 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="657c6-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="657c6-103">이 항목에서는 Visual Basic 비교 및 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 문자열의 문자에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-103">This topic compares how Visual Basic and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="657c6-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Visual Basic 함수에 따라 0부터 시작 하 고 1부터 액세스를 제공 하는 반면 문자열에서 문자에 대 한 0부터 시작 액세스를 항상 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="657c6-105">1부터 시작</span><span class="sxs-lookup"><span data-stu-id="657c6-105">One-Based</span></span>  
 <span data-ttu-id="657c6-106">1부터 Visual Basic 함수 예에 대 한 고려를 `Mid` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="657c6-107">이는 부분 문자열이 시작 되 위치 1부터 시작 문자 위치를 나타내는 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="657c6-108">합니다 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 문자의 인덱스 부분 문자열을 시작 하려면 문자열에서 0의 위치를 사용 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="657c6-109">따라서 "ABCDE" 문자열을 해야 하는 경우 개별 문자 매겨집니다 1,2,3,4,5 사용에 대 한 합니다 `Mid` 함수를 하지만 사용 0,1,2,3,4는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="657c6-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="657c6-110">0부터 시작</span><span class="sxs-lookup"><span data-stu-id="657c6-110">Zero-Based</span></span>  
 <span data-ttu-id="657c6-111">0부터 시작 Visual Basic 함수 예에 대 한 고려를 `Split` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="657c6-112">문자열을 분할 하 고 부분 문자열이 포함 된 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="657c6-113">합니다 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> 메서드는 문자열을 분할 및 부분 문자열이 포함 된 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="657c6-114">때문에 합니다 `Split` 함수 및 <xref:System.String.Split%2A> 메서드가 반환 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 배열 되는 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="657c6-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657c6-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="657c6-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="657c6-116">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="657c6-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
