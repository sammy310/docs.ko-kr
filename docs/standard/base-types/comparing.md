---
title: .NET에서 문자열 비교
description: .NET에서 문자열을 비교하는 메서드에 대해 알아봅니다. CompareOrdinal, CompareTo, StartsWith, EndsWith, Equals, IndexOf, LastIndexOf 메서드에 대해 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- value comparisons of strings
- LastIndexOf method
- CompareTo method
- IndexOf method
- Compare method
- strings [.NET Framework], comparing
- CompareOrdinal method
- EndsWith method
- Equals method
- StartsWith method
ms.assetid: 977dc094-fe19-4955-98ec-d2294d04a4ba
ms.openlocfilehash: 5ed73d18341c3b9c6e61e12fdf322b9a67affd4a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602195"
---
# <a name="comparing-strings-in-net"></a><span data-ttu-id="6aa25-104">.NET에서 문자열 비교</span><span class="sxs-lookup"><span data-stu-id="6aa25-104">Comparing Strings in .NET</span></span>
<span data-ttu-id="6aa25-105">.NET에서는 문자열의 값을 비교하는 여러 가지 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-105">.NET provides several methods to compare the values of strings.</span></span> <span data-ttu-id="6aa25-106">다음 표에서는 값 비교 메서드를 나열하고 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-106">The following table lists and describes the value-comparison methods.</span></span>  
  
|<span data-ttu-id="6aa25-107">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="6aa25-107">Method name</span></span>|<span data-ttu-id="6aa25-108">기능</span><span class="sxs-lookup"><span data-stu-id="6aa25-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Compare%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-109">두 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-109">Compares the values of two strings.</span></span> <span data-ttu-id="6aa25-110">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-110">Returns an integer value.</span></span>|  
|<xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-111">로컬 문화권에 관계없이 두 문자열을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-111">Compares two strings without regard to local culture.</span></span> <span data-ttu-id="6aa25-112">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-112">Returns an integer value.</span></span>|  
|<xref:System.String.CompareTo%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-113">현재 문자열 개체를 다른 문자열과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-113">Compares the current string object to another string.</span></span> <span data-ttu-id="6aa25-114">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-114">Returns an integer value.</span></span>|  
|<xref:System.String.StartsWith%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-115">문자열이 전달된 문자열로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-115">Determines whether a string begins with the string passed.</span></span> <span data-ttu-id="6aa25-116">부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-116">Returns a Boolean value.</span></span>|  
|<xref:System.String.EndsWith%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-117">문자열이 전달된 문자열로 끝나는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-117">Determines whether a string ends with the string passed.</span></span> <span data-ttu-id="6aa25-118">부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-118">Returns a Boolean value.</span></span>|  
|<xref:System.String.Equals%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-119">두 문자열이 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-119">Determines whether two strings are the same.</span></span> <span data-ttu-id="6aa25-120">부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-120">Returns a Boolean value.</span></span>|  
|<xref:System.String.IndexOf%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-121">검사 중인 문자열의 처음부터 시작하여 문자 또는 문자열의 인덱스 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-121">Returns the index position of a character or string, starting from the beginning of the string you are examining.</span></span> <span data-ttu-id="6aa25-122">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-122">Returns an integer value.</span></span>|  
|<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>|<span data-ttu-id="6aa25-123">검사 중인 문자열의 끝부터 시작하여 문자 또는 문자열의 인덱스 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-123">Returns the index position of a character or string, starting from the end of the string you are examining.</span></span> <span data-ttu-id="6aa25-124">정수 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-124">Returns an integer value.</span></span>|  
  
## <a name="compare"></a><span data-ttu-id="6aa25-125">비교</span><span class="sxs-lookup"><span data-stu-id="6aa25-125">Compare</span></span>  
 <span data-ttu-id="6aa25-126">정적 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드는 두 문자열을 비교하는 철저한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-126">The static <xref:System.String.Compare%2A?displayProperty=nameWithType> method provides a thorough way of comparing two strings.</span></span> <span data-ttu-id="6aa25-127">이 메서드는 문화권을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-127">This method is culturally aware.</span></span> <span data-ttu-id="6aa25-128">이 함수를 사용하여 두 문자열 또는 두 문자열의 부분 문자열을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-128">You can use this function to compare two strings or substrings of two strings.</span></span> <span data-ttu-id="6aa25-129">또한 대/소문자와 문화권 차이를 반영하거나 무시하는 오버로드가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-129">Additionally, overloads are provided that regard or disregard case and cultural variance.</span></span> <span data-ttu-id="6aa25-130">다음 표에서는 이 메서드가 반환할 수 있는 세 가지 정수 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-130">The following table shows the three integer values that this method might return.</span></span>  
  
|<span data-ttu-id="6aa25-131">반환 값</span><span class="sxs-lookup"><span data-stu-id="6aa25-131">Return value</span></span>|<span data-ttu-id="6aa25-132">조건</span><span class="sxs-lookup"><span data-stu-id="6aa25-132">Condition</span></span>|  
|------------------|---------------|  
|<span data-ttu-id="6aa25-133">음의 정수</span><span class="sxs-lookup"><span data-stu-id="6aa25-133">A negative integer</span></span>|<span data-ttu-id="6aa25-134">정렬 순서에서 첫 번째 문자열이 두 번째 문자열 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-134">The first string precedes the second string in the sort order.</span></span><br /><br /> <span data-ttu-id="6aa25-135">또는</span><span class="sxs-lookup"><span data-stu-id="6aa25-135">-or-</span></span><br /><br /> <span data-ttu-id="6aa25-136">첫 번째 문자열이 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-136">The first string is `null`.</span></span>|  
|<span data-ttu-id="6aa25-137">0</span><span class="sxs-lookup"><span data-stu-id="6aa25-137">0</span></span>|<span data-ttu-id="6aa25-138">첫 번째 문자열과 두 번째 문자열이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-138">The first string and the second string are equal.</span></span><br /><br /> <span data-ttu-id="6aa25-139">또는</span><span class="sxs-lookup"><span data-stu-id="6aa25-139">-or-</span></span><br /><br /> <span data-ttu-id="6aa25-140">두 문자열이 모두 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-140">Both strings are `null`.</span></span>|  
|<span data-ttu-id="6aa25-141">양의 정수</span><span class="sxs-lookup"><span data-stu-id="6aa25-141">A positive integer</span></span><br /><br /> <span data-ttu-id="6aa25-142">또는</span><span class="sxs-lookup"><span data-stu-id="6aa25-142">-or-</span></span><br /><br /> <span data-ttu-id="6aa25-143">1</span><span class="sxs-lookup"><span data-stu-id="6aa25-143">1</span></span>|<span data-ttu-id="6aa25-144">정렬 순서에서 첫 번째 문자열이 두 번째 문자열 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-144">The first string follows the second string in the sort order.</span></span><br /><br /> <span data-ttu-id="6aa25-145">또는</span><span class="sxs-lookup"><span data-stu-id="6aa25-145">-or-</span></span><br /><br /> <span data-ttu-id="6aa25-146">두 번째 문자열이 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-146">The second string is `null`.</span></span>|  
  
> [!IMPORTANT]
> <span data-ttu-id="6aa25-147"><xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드는 주로 문자열의 순서를 지정하거나 정렬할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-147">The <xref:System.String.Compare%2A?displayProperty=nameWithType> method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="6aa25-148"><xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드를 통해 같은지 여부를 테스트하면 안 됩니다(즉, 한 문자열이 다른 문자열보다 작거나 큰지에 관계없이 반환 값 0을 명시적으로 찾기 위해 사용하면 안 됨).</span><span class="sxs-lookup"><span data-stu-id="6aa25-148">You should not use the <xref:System.String.Compare%2A?displayProperty=nameWithType> method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="6aa25-149">대신, 두 문자열이 같은지 여부를 확인하려면 <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-149">Instead, to determine whether two strings are equal, use the <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6aa25-150">다음 예제에서는 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드를 사용하여 두 문자열의 상대 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-150">The following example uses the <xref:System.String.Compare%2A?displayProperty=nameWithType> method to determine the relative values of two strings.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#6)]
 [!code-csharp[Conceptual.String.BasicOps#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#6)]
 [!code-vb[Conceptual.String.BasicOps#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#6)]  
  
 <span data-ttu-id="6aa25-151">이 예제에서는 콘솔에 `-1` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-151">This example displays `-1` to the console.</span></span>  
  
 <span data-ttu-id="6aa25-152">앞의 예제는 기본적으로 문화권을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-152">The preceding example is culture-sensitive by default.</span></span> <span data-ttu-id="6aa25-153">문화권을 구분하지 않는 문자열 비교를 수행하려면 <xref:System.String.Compare%2A?displayProperty=nameWithType> culture *매개 변수를 제공하여 사용할 문화권을 지정할 수 있게 해주는* 메서드의 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-153">To perform a culture-insensitive string comparison, use an overload of the <xref:System.String.Compare%2A?displayProperty=nameWithType> method that allows you to specify the culture to use by supplying a *culture* parameter.</span></span> <span data-ttu-id="6aa25-154"><xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드를 사용하여 문화권을 구분하지 않는 비교를 수행하는 방법을 보여 주는 예제는 [문화권을 구분하지 않는 문자열 비교 수행](../globalization-localization/performing-culture-insensitive-string-comparisons.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa25-154">For an example that demonstrates how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> method to perform a culture-insensitive comparison, see [Performing Culture-Insensitive String Comparisons](../globalization-localization/performing-culture-insensitive-string-comparisons.md).</span></span>  
  
## <a name="compareordinal"></a><span data-ttu-id="6aa25-155">CompareOrdinal</span><span class="sxs-lookup"><span data-stu-id="6aa25-155">CompareOrdinal</span></span>  
 <span data-ttu-id="6aa25-156"><xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> 메서드는 로컬 문화권을 고려하지 않고 두 문자열 개체를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-156">The <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> method compares two string objects without considering the local culture.</span></span> <span data-ttu-id="6aa25-157">이 메서드의 반환 값은 앞의 표에서 **Compare** 메서드가 반환하는 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-157">The return values of this method are identical to the values returned by the **Compare** method in the previous table.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6aa25-158"><xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> 메서드는 주로 문자열의 순서를 지정하거나 정렬할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-158">The <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="6aa25-159"><xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> 메서드를 통해 같은지 여부를 테스트하면 안 됩니다(즉, 한 문자열이 다른 문자열보다 작거나 큰지에 관계없이 반환 값 0을 명시적으로 찾기 위해 사용하면 안 됨).</span><span class="sxs-lookup"><span data-stu-id="6aa25-159">You should not use the <xref:System.String.CompareOrdinal%2A?displayProperty=nameWithType> method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="6aa25-160">대신, 두 문자열이 같은지 여부를 확인하려면 <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-160">Instead, to determine whether two strings are equal, use the <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6aa25-161">다음 예제에서는 **CompareOrdinal** 메서드를 사용하여 두 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-161">The following example uses the **CompareOrdinal** method to compare the values of two strings.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#7)]
 [!code-csharp[Conceptual.String.BasicOps#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#7)]
 [!code-vb[Conceptual.String.BasicOps#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#7)]  
  
 <span data-ttu-id="6aa25-162">이 예제에서는 콘솔에 `-32` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-162">This example displays `-32` to the console.</span></span>  
  
## <a name="compareto"></a><span data-ttu-id="6aa25-163">CompareTo</span><span class="sxs-lookup"><span data-stu-id="6aa25-163">CompareTo</span></span>  
 <span data-ttu-id="6aa25-164"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드는 현재 문자열 개체가 캡슐화하는 문자열을 다른 문자열 또는 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-164">The <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method compares the string that the current string object encapsulates to another string or object.</span></span> <span data-ttu-id="6aa25-165">이 메서드의 반환 값은 앞의 표에서 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드가 반환하는 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-165">The return values of this method are identical to the values returned by the <xref:System.String.Compare%2A?displayProperty=nameWithType> method in the previous table.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6aa25-166"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드는 주로 문자열의 순서를 지정하거나 정렬할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-166">The <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method is primarily intended for use when ordering or sorting strings.</span></span> <span data-ttu-id="6aa25-167"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드를 통해 같은지 여부를 테스트하면 안 됩니다(즉, 한 문자열이 다른 문자열보다 작거나 큰지에 관계없이 반환 값 0을 명시적으로 찾기 위해 사용하면 안 됨).</span><span class="sxs-lookup"><span data-stu-id="6aa25-167">You should not use the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method to test for equality (that is, to explicitly look for a return value of 0 with no regard for whether one string is less than or greater than the other).</span></span> <span data-ttu-id="6aa25-168">대신, 두 문자열이 같은지 여부를 확인하려면 <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-168">Instead, to determine whether two strings are equal, use the <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="6aa25-169">다음 예제에서는 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드를 사용하여 `string1` 개체를 `string2` 개체와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-169">The following example uses the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method to compare the `string1` object to the `string2` object.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#8)]
 [!code-csharp[Conceptual.String.BasicOps#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#8)]
 [!code-vb[Conceptual.String.BasicOps#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#8)]  
  
 <span data-ttu-id="6aa25-170">이 예제에서는 콘솔에 `-1` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-170">This example displays `-1` to the console.</span></span>  
  
 <span data-ttu-id="6aa25-171"><xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드의 모든 오버로드는 기본적으로 문화권 구분 및 대/소문자 구분 비교 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-171">All overloads of the <xref:System.String.CompareTo%2A?displayProperty=nameWithType> method perform culture-sensitive and case-sensitive comparisons by default.</span></span> <span data-ttu-id="6aa25-172">문화권을 구분하지 않는 비교를 수행할 수 있는 이 메서드의 오버로드는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-172">No overloads of this method are provided that allow you to perform a culture-insensitive comparison.</span></span> <span data-ttu-id="6aa25-173">코드를 이해하기 쉽도록 문화권 구분 작업에는 **를 지정하고 문화권을 구분하지 않는 작업에는** 를 지정하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> String.Compare <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 메서드를 대신하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-173">For code clarity, we recommend that you use the **String.Compare** method instead, specifying <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> for culture-sensitive operations or <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> for culture-insensitive operations.</span></span> <span data-ttu-id="6aa25-174">**String.Compare** 메서드를 사용하여 문화권 구분 비교와 문화권을 구분하지 않는 비교를 둘 다 수행하는 방법을 보여 주는 예제는 [문화권을 구분하지 않는 문자열 비교 수행](../globalization-localization/performing-culture-insensitive-string-comparisons.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6aa25-174">For examples that demonstrate how to use the **String.Compare** method to perform both culture-sensitive and culture-insensitive comparisons, see [Performing Culture-Insensitive String Comparisons](../globalization-localization/performing-culture-insensitive-string-comparisons.md).</span></span>  
  
## <a name="equals"></a><span data-ttu-id="6aa25-175">같음</span><span class="sxs-lookup"><span data-stu-id="6aa25-175">Equals</span></span>  
 <span data-ttu-id="6aa25-176">**String.Equals** 메서드는 두 문자열이 같은지 여부를 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-176">The **String.Equals** method can easily determine if two strings are the same.</span></span> <span data-ttu-id="6aa25-177">대/소문자 구분 메서드는 **true** 또는 **false** 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-177">This case-sensitive method returns a **true** or **false** Boolean value.</span></span> <span data-ttu-id="6aa25-178">다음 예제와 같이 기존 클래스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-178">It can be used from an existing class, as illustrated in the next example.</span></span> <span data-ttu-id="6aa25-179">다음 예제에서는 **Equals** 메서드를 사용하여 문자열 개체에 "Hello World"라는 구가 포함되어 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-179">The following example uses the **Equals** method to determine whether a string object contains the phrase "Hello World".</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#9)]
 [!code-csharp[Conceptual.String.BasicOps#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#9)]
 [!code-vb[Conceptual.String.BasicOps#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#9)]  
  
 <span data-ttu-id="6aa25-180">이 예제에서는 콘솔에 `True` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-180">This example displays `True` to the console.</span></span>  
  
 <span data-ttu-id="6aa25-181">이 메서드는 정적 메서드로 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-181">This method can also be used as a static method.</span></span> <span data-ttu-id="6aa25-182">다음 예제에서는 정적 메서드를 사용하여 두 문자열 개체를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-182">The following example compares two string objects using a static method.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#10)]
 [!code-csharp[Conceptual.String.BasicOps#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#10)]
 [!code-vb[Conceptual.String.BasicOps#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#10)]  
  
 <span data-ttu-id="6aa25-183">이 예제에서는 콘솔에 `True` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-183">This example displays `True` to the console.</span></span>  
  
## <a name="startswith-and-endswith"></a><span data-ttu-id="6aa25-184">StartsWith 및 EndsWith</span><span class="sxs-lookup"><span data-stu-id="6aa25-184">StartsWith and EndsWith</span></span>  
 <span data-ttu-id="6aa25-185">**String.StartsWith** 메서드를 사용하여 문자열 개체가 다른 문자열을 포함하는 동일한 문자로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-185">You can use the **String.StartsWith** method to determine whether a string object begins with the same characters that encompass another string.</span></span> <span data-ttu-id="6aa25-186">이 대/소문자 구분 메서드는 현재 문자열 개체가 전달된 문자열로 시작하는 경우 **true** 를 반환하고, 그러지 않은 경우 **false** 를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-186">This case-sensitive method returns **true** if the current string object begins with the passed string and **false** if it does not.</span></span> <span data-ttu-id="6aa25-187">다음 예제에서는 이 메서드를 사용하여 문자열 개체가 "Hello"로 시작하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-187">The following example uses this method to determine if a string object begins with "Hello".</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#11)]
 [!code-csharp[Conceptual.String.BasicOps#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#11)]
 [!code-vb[Conceptual.String.BasicOps#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#11)]  
  
 <span data-ttu-id="6aa25-188">이 예제에서는 콘솔에 `True` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-188">This example displays `True` to the console.</span></span>  
  
 <span data-ttu-id="6aa25-189">**String.EndsWith** 메서드는 전달된 문자열을 현재 문자열 개체의 끝에 있는 문자와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-189">The **String.EndsWith** method compares a passed string to the characters that exist at the end of the current string object.</span></span> <span data-ttu-id="6aa25-190">역시 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-190">It also returns a Boolean value.</span></span> <span data-ttu-id="6aa25-191">다음 예제에서는 **EndsWith** 메서드를 사용하여 문자열의 끝을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-191">The following example checks the end of a string using the **EndsWith** method.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#12)]
 [!code-csharp[Conceptual.String.BasicOps#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#12)]
 [!code-vb[Conceptual.String.BasicOps#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#12)]  
  
 <span data-ttu-id="6aa25-192">이 예제에서는 콘솔에 `False` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-192">This example displays `False` to the console.</span></span>  
  
## <a name="indexof-and-lastindexof"></a><span data-ttu-id="6aa25-193">IndexOf 및 LastIndexOf</span><span class="sxs-lookup"><span data-stu-id="6aa25-193">IndexOf and LastIndexOf</span></span>  
 <span data-ttu-id="6aa25-194">**String.IndexOf** 메서드를 사용하여 문자열 내에서 특정 문자의 첫 번째 발생 위치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-194">You can use the **String.IndexOf** method to determine the position of the first occurrence of a particular character within a string.</span></span> <span data-ttu-id="6aa25-195">이 대/소문자 구분 메서드는 문자열의 시작 부분에서 계산을 시작하고 0부터 시작하는 인덱스를 사용하여 전달된 문자의 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-195">This case-sensitive method starts counting from the beginning of a string and returns the position of a passed character using a zero-based index.</span></span> <span data-ttu-id="6aa25-196">문자를 찾을 수 없는 경우 -1 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-196">If the character cannot be found, a value of –1 is returned.</span></span>  
  
 <span data-ttu-id="6aa25-197">다음 예제에서는 **IndexOf** 메서드를 사용하여 문자열에서 '`l`' 문자의 첫 번째 발생을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-197">The following example uses the **IndexOf** method to search for the first occurrence of the '`l`' character in a string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#13)]
 [!code-csharp[Conceptual.String.BasicOps#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#13)]
 [!code-vb[Conceptual.String.BasicOps#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#13)]  
  
 <span data-ttu-id="6aa25-198">이 예제에서는 콘솔에 `2` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-198">This example displays `2` to the console.</span></span>  
  
 <span data-ttu-id="6aa25-199">**String.LastIndexOf** 메서드는 문자열 내에서 특정 문자의 마지막 발생 위치를 반환한다는 점을 제외하고 **String.IndexOf** 메서드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-199">The **String.LastIndexOf** method is similar to the **String.IndexOf** method except that it returns the position of the last occurrence of a particular character within a string.</span></span> <span data-ttu-id="6aa25-200">대/소문자를 구분하며 0부터 시작하는 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-200">It is case-sensitive and uses a zero-based index.</span></span>  
  
 <span data-ttu-id="6aa25-201">다음 예제에서는 **LastIndexOf** 메서드를 사용하여 문자열에서 '`l`' 문자의 마지막 발생을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-201">The following example uses the **LastIndexOf** method to search for the last occurrence of the '`l`' character in a string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/compare.cpp#14)]
 [!code-csharp[Conceptual.String.BasicOps#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/compare.cs#14)]
 [!code-vb[Conceptual.String.BasicOps#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/compare.vb#14)]  
  
 <span data-ttu-id="6aa25-202">이 예제에서는 콘솔에 `9` 를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-202">This example displays `9` to the console.</span></span>  
  
 <span data-ttu-id="6aa25-203">두 메서드는 모두 **String.Remove** 메서드와 함께 사용할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-203">Both methods are useful when used in conjunction with the **String.Remove** method.</span></span> <span data-ttu-id="6aa25-204">문자 또는 해당 문자로 시작하는 단어를 제거하기 위해 **IndexOf** 또는 **LastIndexOf** 메서드 중 하나를 사용하여 문자의 위치를 검색한 다음 해당 위치를 **Remove** 메서드에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6aa25-204">You can use either the **IndexOf** or **LastIndexOf** methods to retrieve the position of a character, and then supply that position to the **Remove** method in order to remove a character or a word that begins with that character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa25-205">참조</span><span class="sxs-lookup"><span data-stu-id="6aa25-205">See also</span></span>

- [<span data-ttu-id="6aa25-206">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="6aa25-206">Basic String Operations</span></span>](basic-string-operations.md)
- [<span data-ttu-id="6aa25-207">Culture의 영향을 받지 않는 문자열 작업 수행</span><span class="sxs-lookup"><span data-stu-id="6aa25-207">Performing Culture-Insensitive String Operations</span></span>](../globalization-localization/performing-culture-insensitive-string-operations.md)
- [<span data-ttu-id="6aa25-208">정렬 가중치 테이블(Windows의 .NET용)</span><span class="sxs-lookup"><span data-stu-id="6aa25-208">Sorting Weight Tables (for .NET on Windows)</span></span>](https://www.microsoft.com/download/details.aspx?id=10921)
- [<span data-ttu-id="6aa25-209">기본 유니코드 데이터 정렬 요소 테이블(Linux 및 macOS의 .NET Core용)</span><span class="sxs-lookup"><span data-stu-id="6aa25-209">Default Unicode Collation Element Table (for .NET Core on Linux and macOS)</span></span>](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
