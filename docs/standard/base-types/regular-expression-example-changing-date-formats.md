---
title: '정규식 예제: 날짜 형식 변경'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: 4290bf0d6ee9deec8129c5f4f6092eedb08345f0
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276181"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="aa466-102">정규식 예제: 날짜 형식 변경</span><span class="sxs-lookup"><span data-stu-id="aa466-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="aa466-103">다음 코드 예제에서는 <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> 메서드를 사용하여 *mm*/*dd*/*yy* 형식의 날짜를 *dd*-*mm*-*yy* 형식의 날짜로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy*.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa466-104">예제</span><span class="sxs-lookup"><span data-stu-id="aa466-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="aa466-105">다음 코드에서는 애플리케이션에서 `MDYToDMY` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="aa466-106">설명</span><span class="sxs-lookup"><span data-stu-id="aa466-106">Comments</span></span>  
 <span data-ttu-id="aa466-107">정규식 패턴 `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b`는 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="aa466-108">무늬</span><span class="sxs-lookup"><span data-stu-id="aa466-108">Pattern</span></span>|<span data-ttu-id="aa466-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa466-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="aa466-110">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="aa466-111">한 개 또는 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-111">Match one or two decimal digits.</span></span> <span data-ttu-id="aa466-112">캡처된 `month` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="aa466-113">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="aa466-114">한 개 또는 두 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-114">Match one or two decimal digits.</span></span> <span data-ttu-id="aa466-115">캡처된 `day` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="aa466-116">슬래시 기호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="aa466-117">2~4개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="aa466-118">캡처된 `year` 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="aa466-119">단어 경계에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="aa466-120">`${day}-${month}-${year}` 패턴은 다음 표와 같이 대체 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="aa466-121">무늬</span><span class="sxs-lookup"><span data-stu-id="aa466-121">Pattern</span></span>|<span data-ttu-id="aa466-122">설명</span><span class="sxs-lookup"><span data-stu-id="aa466-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="aa466-123">`day` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="aa466-124">하이픈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="aa466-125">`month` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="aa466-126">하이픈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="aa466-127">`year` 캡처링 그룹에 의해 캡처된 부분 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aa466-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa466-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa466-128">See also</span></span>

- [<span data-ttu-id="aa466-129">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="aa466-129">.NET Regular Expressions</span></span>](regular-expressions.md)
