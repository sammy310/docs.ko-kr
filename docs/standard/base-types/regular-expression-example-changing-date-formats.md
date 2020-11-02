---
title: '정규식 예제: 날짜 형식 변경'
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: b5eca8c294349fada9cfb1cb3ed8e2012edd8bda
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889415"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="95922-102">정규식 예제: 날짜 형식 변경</span><span class="sxs-lookup"><span data-stu-id="95922-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="95922-103">다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 메서드를 사용하여 *mm*/*dd*/*yy* 형식의 날짜를 *dd*-*mm*-*yy* 형식의 날짜로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="95922-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy* .</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="95922-104">예제</span><span class="sxs-lookup"><span data-stu-id="95922-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="95922-105">다음 코드에서는 애플리케이션에서 `MDYToDMY` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95922-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="95922-106">설명</span><span class="sxs-lookup"><span data-stu-id="95922-106">Comments</span></span>  
 <span data-ttu-id="95922-107">정규식 패턴 `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b`는 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="95922-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="95922-108">무늬</span><span class="sxs-lookup"><span data-stu-id="95922-108">Pattern</span></span>|<span data-ttu-id="95922-109">설명</span><span class="sxs-lookup"><span data-stu-id="95922-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="95922-110">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="95922-111">한 개 또는 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95922-111">Match one or two decimal digits.</span></span> <span data-ttu-id="95922-112">캡처된 `month` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="95922-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="95922-113">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95922-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="95922-114">한 개 또는 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95922-114">Match one or two decimal digits.</span></span> <span data-ttu-id="95922-115">캡처된 `day` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="95922-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="95922-116">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95922-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="95922-117">2~4개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="95922-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="95922-118">캡처된 `year` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="95922-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="95922-119">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="95922-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="95922-120">`${day}-${month}-${year}` 패턴은 다음 표와 같이 대체 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="95922-121">무늬</span><span class="sxs-lookup"><span data-stu-id="95922-121">Pattern</span></span>|<span data-ttu-id="95922-122">설명</span><span class="sxs-lookup"><span data-stu-id="95922-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="95922-123">`day` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="95922-124">하이픈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="95922-125">`month` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="95922-126">하이픈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="95922-127">`year` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="95922-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95922-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95922-128">See also</span></span>

- [<span data-ttu-id="95922-129">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="95922-129">.NET Regular Expressions</span></span>](regular-expressions.md)
