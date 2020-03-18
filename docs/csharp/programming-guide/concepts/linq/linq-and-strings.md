---
title: LINQ 및 문자열(C#)
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: b805bc7318b8c5fe70ab1c060d1058a6bbc4f177
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635537"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="20189-102">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-102">LINQ and strings (C#)</span></span>

<span data-ttu-id="20189-103">LINQ를 사용하여 문자열 및 문자열 컬렉션을 쿼리하고 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="20189-104">텍스트 파일의 반구조적 데이터에 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="20189-105">LINQ 쿼리에 기존의 문자열 함수 및 정규식을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="20189-106">예를 들어 <xref:System.String.Split%2A?displayProperty=nameWithType> 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 문자열 배열을 만든 다음 LINQ를 사용하여 쿼리하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-106">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="20189-107">LINQ 쿼리의 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> 절에 `where` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="20189-108">또한 LINQ를 사용하여 정규식에서 반환된 <xref:System.Text.RegularExpressions.MatchCollection> 결과를 쿼리하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="20189-109">이 섹션에 설명된 기법을 사용하여 반구조적 텍스트 데이터를 XML로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="20189-110">자세한 내용은 [CSV 파일에서 XML을 생성하는 방법](how-to-generate-xml-from-csv-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20189-110">For more information, see [How to generate XML from CSV files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="20189-111">이 섹션의 예제는 다음 두 가지 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="20189-111">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="20189-112">텍스트 블록 쿼리</span><span class="sxs-lookup"><span data-stu-id="20189-112">Querying a block of text</span></span>

<span data-ttu-id="20189-113"><xref:System.String.Split%2A?displayProperty=nameWithType> 메서드 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 더 작은 문자열의 쿼리 가능 배열로 분할하면 텍스트 블록을 쿼리, 분석, 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="20189-114">소스 텍스트를 단어, 문장, 단락, 페이지 또는 기타 기준으로 분할한 다음 쿼리에 필요한 경우 추가 분할을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="20189-115">문자열에서 단어가 나오는 횟수를 세는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-115">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="20189-116">간단한 텍스트 쿼리를 위해 LINQ를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-116">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="20189-117">지정된 단어 집합이 들어 있는 문장을 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-117">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="20189-118">임의의 경계에서 텍스트 파일을 분할하는 방법 및 각 부분에 대해 쿼리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="20189-119">문자열의 문자를 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-119">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="20189-120">문자열이 쿼리 가능한 형식인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-120">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="20189-121">LINQ 쿼리와 정규식 결합 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-121">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="20189-122">필터링된 쿼리 결과에 대한 복잡한 패턴 일치를 위해 LINQ 쿼리에서 정규식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="20189-123">텍스트 형식의 반구조적 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="20189-123">Querying semi-structured data in text format</span></span>

<span data-ttu-id="20189-124">다양한 형식의 텍스트 파일은 대체로 탭 또는 쉼표로 구분된 파일 또는 고정 길이 줄과 같은 유사한 형식을 가진 일련의 줄로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="20189-125">이러한 텍스트 파일을 메모리로 읽어온 후 LINQ를 사용하여 줄을 쿼리 및/또는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20189-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="20189-126">또한 LINQ 쿼리는 여러 소스의 데이터를 결합하는 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="20189-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="20189-127">두 목록 간의 차집합을 구하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-127">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="20189-128">한 목록에는 있지만 다른 목록에는 없는 모든 문자열을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-128">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="20189-129">단어 또는 필드에 따라 텍스트 데이터를 정렬하거나 필터링하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-129">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="20189-130">단어 또는 필드에 따라 텍스트 줄을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-130">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="20189-131">구분된 파일의 필드를 다시 정렬하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-131">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="20189-132">.csv 파일에서 줄의 필드 순서를 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-132">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="20189-133">문자열 컬렉션의 결합 및 비교 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-133">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="20189-134">다양한 방법으로 문자열 목록을 조합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-134">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="20189-135">여러 소스로 개체 컬렉션을 채우는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-135">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="20189-136">여러 텍스트 파일을 데이터 소스로 사용하여 개체 컬렉션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-136">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="20189-137">서로 다른 파일의 콘텐츠를 조인하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-137">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="20189-138">일치하는 키를 사용하여 두 목록의 문자열을 단일 문자열로 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="20189-139">그룹을 사용하여 파일을 여러 파일로 분할하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-139">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="20189-140">단일 파일을 데이터 소스로 사용하여 새 파일을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-140">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="20189-141">CSV 텍스트 파일의 열 값을 컴퓨팅하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-141">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="20189-142">.csv 파일의 텍스트 데이터에 대해 수학적 계산을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20189-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="20189-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20189-143">See also</span></span>

- [<span data-ttu-id="20189-144">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="20189-144">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="20189-145">CSV 파일에서 XML을 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="20189-145">How to generate XML from CSV files</span></span>](how-to-generate-xml-from-csv-files.md)
