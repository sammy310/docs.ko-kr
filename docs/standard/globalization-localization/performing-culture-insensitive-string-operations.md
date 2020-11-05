---
title: Culture의 영향을 받지 않는 문자열 작업 수행
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: 0f7e8dde395feb548e6808547a223a3fa8855561
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063913"
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="4f4d3-102">문화권의 영향을 받지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="4f4d3-102">Performing culture-insensitive string operations</span></span>

<span data-ttu-id="4f4d3-103">문화권 구분 문자열 작업을 수행하는 대부분의 .NET 메서드는 기본적으로 <xref:System.Globalization.CultureInfo> 매개 변수를 전달하여 사용할 문화권을 명시적으로 지정할 수 있도록 하는 메서드 오버로드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-103">Most .NET methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="4f4d3-104">이러한 오버로드를 사용하여 매핑 및 정렬 규칙이 문화권을 구분하지 않는 결과를 보장할 경우 문화권 변동을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="4f4d3-105">이 섹션에서는 기본적으로 문화권을 구분하는 .NET 메서드를 사용하여 문화권을 구분하지 않는 문자열 작업을 수행하는 방법을 보여 주기 위해 다음 문서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-105">This section provides the following articles to demonstrate how to perform culture-insensitive string operations using .NET methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f4d3-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4f4d3-106">In this section</span></span>  
 [<span data-ttu-id="4f4d3-107">문화권을 구분하지 않는 문자열 비교 수행</span><span class="sxs-lookup"><span data-stu-id="4f4d3-107">Performing Culture-Insensitive String Comparisons</span></span>](performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="4f4d3-108"><xref:System.String.Compare%2A?displayProperty=nameWithType> 및 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드를 사용하여 문화권을 구분하지 않는 문자열 비교를 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="4f4d3-109">문화권을 구분하지 않는 대/소문자 변경 수행</span><span class="sxs-lookup"><span data-stu-id="4f4d3-109">Performing Culture-Insensitive Case Changes</span></span>](performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="4f4d3-110"><xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> 및 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 메서드를 사용하여 문화권을 구분하지 않는 대/소문자 변경을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="4f4d3-111">컬렉션에서 문화권을 구분하지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="4f4d3-111">Performing Culture-Insensitive String Operations in Collections</span></span>](performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="4f4d3-112"><xref:System.Collections.CaseInsensitiveComparer> 및 <xref:System.Collections.CaseInsensitiveHashCodeProvider> 클래스, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> 메서드를 사용하여 컬렉션에서 문화권을 구분하지 않는 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="4f4d3-113">배열에서 문화권을 구분하지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="4f4d3-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="4f4d3-114"><xref:System.Array.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 메서드를 사용하여 배열에서 문화권을 구분하지 않는 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4f4d3-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4f4d3-115">Related sections</span></span>  
 [<span data-ttu-id="4f4d3-116">문화권을 구분하지 않는 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="4f4d3-116">Culture-Insensitive String Operations</span></span>](culture-insensitive-string-operations.md)  
 <span data-ttu-id="4f4d3-117">문자열에 대해 작업을 수행할 때 문화권을 알아야 하는 이유를 설명하고 문화권 구분 작업을 수행해야 하는 경우 및 문화권을 구분하지 않는 작업을 수행해야 하는 경우에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f4d3-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f4d3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f4d3-118">See also</span></span>

- [<span data-ttu-id="4f4d3-119">정렬 가중치 테이블(Windows 시스템의 .NET용)</span><span class="sxs-lookup"><span data-stu-id="4f4d3-119">Sorting Weight Tables (for .NET on Windows systems)</span></span>](https://www.microsoft.com/download/details.aspx?id=10921)
- [<span data-ttu-id="4f4d3-120">기본 유니코드 데이터 정렬 요소 테이블(Linux 및 macOS의 .NET Core용)</span><span class="sxs-lookup"><span data-stu-id="4f4d3-120">Default Unicode Collation Element Table (for .NET Core on Linux and macOS)</span></span>](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
