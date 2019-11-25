---
title: Zero-based vs. One-based String Access
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354296"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="f26b3-102">Visual Basic에서 0부터 시작하는 문자열 액세스와 1부터 시작하는 문자열 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="f26b3-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="f26b3-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span><span class="sxs-lookup"><span data-stu-id="f26b3-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="f26b3-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span><span class="sxs-lookup"><span data-stu-id="f26b3-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="f26b3-105">One-Based</span><span class="sxs-lookup"><span data-stu-id="f26b3-105">One-Based</span></span>  
 <span data-ttu-id="f26b3-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span><span class="sxs-lookup"><span data-stu-id="f26b3-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="f26b3-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span><span class="sxs-lookup"><span data-stu-id="f26b3-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="f26b3-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span><span class="sxs-lookup"><span data-stu-id="f26b3-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="f26b3-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span><span class="sxs-lookup"><span data-stu-id="f26b3-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="f26b3-110">Zero-Based</span><span class="sxs-lookup"><span data-stu-id="f26b3-110">Zero-Based</span></span>  
 <span data-ttu-id="f26b3-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span><span class="sxs-lookup"><span data-stu-id="f26b3-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="f26b3-112">It splits a string and returns an array containing the substrings.</span><span class="sxs-lookup"><span data-stu-id="f26b3-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="f26b3-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span><span class="sxs-lookup"><span data-stu-id="f26b3-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="f26b3-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span><span class="sxs-lookup"><span data-stu-id="f26b3-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f26b3-115">참조</span><span class="sxs-lookup"><span data-stu-id="f26b3-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="f26b3-116">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="f26b3-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
