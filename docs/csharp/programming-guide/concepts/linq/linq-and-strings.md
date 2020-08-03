---
title: LINQ 및 문자열(C#)
description: LINQ는 문자열 및 문자열 컬렉션을 쿼리하고 변환할 수 있습니다. LINQ 쿼리와 C# 문자열 함수 및 정규식을 결합할 수 있습니다.
ms.date: 07/20/2015
ms.assetid: dbe2d657-b3f3-487e-b645-21fb2d71cd7b
ms.openlocfilehash: c515a0c56ad6473f93c6339540e4ed0245bb5bd2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165616"
---
# <a name="linq-and-strings-c"></a><span data-ttu-id="20128-104">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-104">LINQ and strings (C#)</span></span>

<span data-ttu-id="20128-105">LINQ를 사용하여 문자열 및 문자열 컬렉션을 쿼리하고 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-105">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="20128-106">텍스트 파일의 반구조적 데이터에 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-106">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="20128-107">LINQ 쿼리에 기존의 문자열 함수 및 정규식을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-107">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="20128-108">예를 들어 <xref:System.String.Split%2A?displayProperty=nameWithType> 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 문자열 배열을 만든 다음 LINQ를 사용하여 쿼리하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-108">For example, you can use the <xref:System.String.Split%2A?displayProperty=nameWithType> or <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="20128-109">LINQ 쿼리의 `where` 절에 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-109">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="20128-110">또한 LINQ를 사용하여 정규식에서 반환된 <xref:System.Text.RegularExpressions.MatchCollection> 결과를 쿼리하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-110">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>

<span data-ttu-id="20128-111">이 섹션에 설명된 기법을 사용하여 반구조적 텍스트 데이터를 XML로 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-111">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="20128-112">자세한 내용은 [CSV 파일에서 XML을 생성하는 방법](how-to-generate-xml-from-csv-files.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20128-112">For more information, see [How to generate XML from CSV files](how-to-generate-xml-from-csv-files.md).</span></span>

<span data-ttu-id="20128-113">이 섹션의 예제는 다음 두 가지 범주로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="20128-113">The examples in this section fall into two categories:</span></span>

## <a name="querying-a-block-of-text"></a><span data-ttu-id="20128-114">텍스트 블록 쿼리</span><span class="sxs-lookup"><span data-stu-id="20128-114">Querying a block of text</span></span>

<span data-ttu-id="20128-115"><xref:System.String.Split%2A?displayProperty=nameWithType> 메서드 또는 <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 더 작은 문자열의 쿼리 가능 배열로 분할하면 텍스트 블록을 쿼리, 분석, 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-115">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A?displayProperty=nameWithType> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="20128-116">소스 텍스트를 단어, 문장, 단락, 페이지 또는 기타 기준으로 분할한 다음 쿼리에 필요한 경우 추가 분할을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-116">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>

- [<span data-ttu-id="20128-117">문자열에서 단어가 나오는 횟수를 세는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-117">How to count occurrences of a word in a string (LINQ) (C#)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
  <span data-ttu-id="20128-118">간단한 텍스트 쿼리를 위해 LINQ를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-118">Shows how to use LINQ for simple querying over text.</span></span>

- [<span data-ttu-id="20128-119">지정된 단어 집합이 들어 있는 문장을 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-119">How to query for sentences that contain a specified set of words (LINQ) (C#)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)

  <span data-ttu-id="20128-120">임의의 경계에서 텍스트 파일을 분할하는 방법 및 각 부분에 대해 쿼리를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-120">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>

- [<span data-ttu-id="20128-121">문자열의 문자를 쿼리하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-121">How to query for characters in a string (LINQ) (C#)</span></span>](how-to-query-for-characters-in-a-string-linq.md)

  <span data-ttu-id="20128-122">문자열이 쿼리 가능한 형식인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-122">Demonstrates that a string is a queryable type.</span></span>

- [<span data-ttu-id="20128-123">LINQ 쿼리와 정규식 결합 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-123">How to combine LINQ queries with regular expressions (C#)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)

  <span data-ttu-id="20128-124">필터링된 쿼리 결과에 대한 복잡한 패턴 일치를 위해 LINQ 쿼리에서 정규식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-124">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>

## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="20128-125">텍스트 형식의 반구조적 데이터 쿼리</span><span class="sxs-lookup"><span data-stu-id="20128-125">Querying semi-structured data in text format</span></span>

<span data-ttu-id="20128-126">다양한 형식의 텍스트 파일은 대체로 탭 또는 쉼표로 구분된 파일 또는 고정 길이 줄과 같은 유사한 형식을 가진 일련의 줄로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-126">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="20128-127">이러한 텍스트 파일을 메모리로 읽어온 후 LINQ를 사용하여 줄을 쿼리 및/또는 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20128-127">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="20128-128">또한 LINQ 쿼리는 여러 소스의 데이터를 결합하는 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="20128-128">LINQ queries also simplify the task of combining data from multiple sources.</span></span>

- [<span data-ttu-id="20128-129">두 목록 간의 차집합을 구하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-129">How to find the set difference between two lists (LINQ) (C#)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)

  <span data-ttu-id="20128-130">한 목록에는 있지만 다른 목록에는 없는 모든 문자열을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-130">Shows how to find all the strings that are present in one list but not the other.</span></span>

- [<span data-ttu-id="20128-131">단어 또는 필드에 따라 텍스트 데이터를 정렬하거나 필터링하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-131">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)

  <span data-ttu-id="20128-132">단어 또는 필드에 따라 텍스트 줄을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-132">Shows how to sort text lines based on any word or field.</span></span>

- [<span data-ttu-id="20128-133">구분된 파일의 필드를 다시 정렬하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-133">How to reorder the fields of a delimited file (LINQ) (C#)</span></span>](how-to-reorder-the-fields-of-a-delimited-file-linq.md)

  <span data-ttu-id="20128-134">.csv 파일에서 줄의 필드 순서를 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-134">Shows how to reorder fields in a line in a .csv file.</span></span>

- [<span data-ttu-id="20128-135">문자열 컬렉션의 결합 및 비교 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-135">How to combine and compare string collections (LINQ) (C#)</span></span>](how-to-combine-and-compare-string-collections-linq.md)

  <span data-ttu-id="20128-136">다양한 방법으로 문자열 목록을 조합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-136">Shows how to combine string lists in various ways.</span></span>

- [<span data-ttu-id="20128-137">여러 소스로 개체 컬렉션을 채우는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-137">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)

  <span data-ttu-id="20128-138">여러 텍스트 파일을 데이터 소스로 사용하여 개체 컬렉션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-138">Shows how to create object collections by using multiple text files as data sources.</span></span>

- [<span data-ttu-id="20128-139">서로 다른 파일의 콘텐츠를 조인하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-139">How to join content from dissimilar files (LINQ) (C#)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)
  
  <span data-ttu-id="20128-140">일치하는 키를 사용하여 두 목록의 문자열을 단일 문자열로 결합하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-140">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>

- [<span data-ttu-id="20128-141">그룹을 사용하여 파일을 여러 파일로 분할하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-141">How to split a file into many files by using groups (LINQ) (C#)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
  
  <span data-ttu-id="20128-142">단일 파일을 데이터 소스로 사용하여 새 파일을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-142">Shows how to create new files by using a single file as a data source.</span></span>

- [<span data-ttu-id="20128-143">CSV 텍스트 파일의 열 값을 컴퓨팅하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-143">How to compute column values in a CSV text file (LINQ) (C#)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)
  
  <span data-ttu-id="20128-144">.csv 파일의 텍스트 데이터에 대해 수학적 계산을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20128-144">Shows how to perform mathematical computations on text data in .csv files.</span></span>

## <a name="see-also"></a><span data-ttu-id="20128-145">참조</span><span class="sxs-lookup"><span data-stu-id="20128-145">See also</span></span>

- [<span data-ttu-id="20128-146">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="20128-146">Language-Integrated Query (LINQ) (C#)</span></span>](index.md)
- [<span data-ttu-id="20128-147">CSV 파일에서 XML을 생성하는 방법</span><span class="sxs-lookup"><span data-stu-id="20128-147">How to generate XML from CSV files</span></span>](how-to-generate-xml-from-csv-files.md)
