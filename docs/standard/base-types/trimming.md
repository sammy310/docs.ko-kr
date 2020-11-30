---
title: .NET에서 문자열의 문자 트리밍 및 제거
description: .NET에서 문자열의 시작 또는 끝부분에서 공백을 자르거나 문자열의 지정된 위치에서 공백 또는 문자를 제거하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], removing characters
- Remove method
- TrimEnd method
- Trim method
- trimming characters
- TrimStart method
- removing characters
ms.assetid: ab248dab-70d4-4413-81c6-542d153fd195
ms.openlocfilehash: 9b0fd87bfec747f8dd09d3972167374a1a2daffa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734191"
---
# <a name="trimming-and-removing-characters-from-strings-in-net"></a><span data-ttu-id="008e7-103">.NET에서 문자열의 문자 트리밍 및 제거</span><span class="sxs-lookup"><span data-stu-id="008e7-103">Trimming and Removing Characters from Strings in .NET</span></span>

<span data-ttu-id="008e7-104">문장을 개별 단어로 구문 분석할 경우 단어의 끝에 빈 공간(공백이라고도 함)이 있는 단어가 생길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-104">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="008e7-105">이 경우에 **System.String** 클래스에서 trim 메서드 중 하나를 사용하여 문자열에 지정된 위치에서 공백의 수나 다른 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-105">In this situation, you can use one of the trim methods in the **System.String** class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="008e7-106">다음 테이블에서는 사용할 수 있는 trim 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-106">The following table describes the available trim methods.</span></span>  
  
|<span data-ttu-id="008e7-107">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="008e7-107">Method name</span></span>|<span data-ttu-id="008e7-108">기능</span><span class="sxs-lookup"><span data-stu-id="008e7-108">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Trim%2A?displayProperty=nameWithType>|<span data-ttu-id="008e7-109">문자열의 시작과 끝에서 문자 배열에 지정된 문자 또는 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-109">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>|  
|<xref:System.String.TrimEnd%2A?displayProperty=nameWithType>|<span data-ttu-id="008e7-110">문자열의 끝에서 문자 배열에 지정된 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-110">Removes characters specified in an array of characters from the end of a string.</span></span>|  
|<xref:System.String.TrimStart%2A?displayProperty=nameWithType>|<span data-ttu-id="008e7-111">문자열의 시작에서 문자 배열에 지정된 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-111">Removes characters specified in an array of characters from the beginning of a string.</span></span>|  
|<xref:System.String.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="008e7-112">문자열의 지정한 인덱스 위치에서 지정한 개수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-112">Removes a specified number of characters from a specified index position in a string.</span></span>|  
  
## <a name="trim"></a><span data-ttu-id="008e7-113">Trim</span><span class="sxs-lookup"><span data-stu-id="008e7-113">Trim</span></span>

 <span data-ttu-id="008e7-114">다음 예제와 같이 <xref:System.String.Trim%2A?displayProperty=nameWithType> 메서드를 사용하여 문자열의 양쪽 끝에서 공백을 쉽게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-114">You can easily remove white spaces from both ends of a string by using the <xref:System.String.Trim%2A?displayProperty=nameWithType> method, as shown in the following example.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#17)]
 [!code-csharp[Conceptual.String.BasicOps#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#17)]
 [!code-vb[Conceptual.String.BasicOps#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#17)]  
  
 <span data-ttu-id="008e7-115">문자열의 시작과 끝의 문자 배열에서 지정하는 문자를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-115">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="008e7-116">다음 예제에서는 공백 문자, 마침표 또는 별표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-116">The following example removes white-space characters, periods, and asterisks.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#22](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trim2.cs#22)]
 [!code-vb[Conceptual.String.BasicOps#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trim2.vb#22)]  
  
## <a name="trimend"></a><span data-ttu-id="008e7-117">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="008e7-117">TrimEnd</span></span>

 <span data-ttu-id="008e7-118">**String.TrimEnd** 메서드는 새 문자열 개체를 생성하여 문자열의 끝에서 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-118">The **String.TrimEnd** method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="008e7-119">문자 배열을 이 메서드에 전달하여 제거할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-119">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="008e7-120">문자 배열에서 요소의 순서는 trim 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-120">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="008e7-121">배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-121">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="008e7-122">다음 예제에서는 **TrimEnd** 메서드를 사용하여 문자열의 마지막 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-122">The following example removes the last letters of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="008e7-123">이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'r'` 문자 및 `'W'` 문자의 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-123">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="008e7-124">이 코드는 `MyString`의 마지막 단어 및 첫 번째 단어의 일부를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-124">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#18)]
 [!code-csharp[Conceptual.String.BasicOps#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#18)]
 [!code-vb[Conceptual.String.BasicOps#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#18)]  
  
 <span data-ttu-id="008e7-125">이 코드는 콘솔에 `He`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-125">This code displays `He` to the console.</span></span>  
  
 <span data-ttu-id="008e7-126">다음 예제에서는 **TrimEnd** 메서드를 사용하여 문자열의 마지막 단어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-126">The following example removes the last word of a string using the **TrimEnd** method.</span></span> <span data-ttu-id="008e7-127">이 코드에서 쉼표는 `Hello` 단어 뒤에 오면 쉼표가 trim에 대한 문자의 배열에 지정되지 않기 때문에 해당 trim은 쉼표에서 끝나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-127">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#19)]
 [!code-csharp[Conceptual.String.BasicOps#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#19)]
 [!code-vb[Conceptual.String.BasicOps#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#19)]  
  
 <span data-ttu-id="008e7-128">이 코드는 콘솔에 `Hello,`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-128">This code displays `Hello,` to the console.</span></span>  
  
## <a name="trimstart"></a><span data-ttu-id="008e7-129">TrimStart</span><span class="sxs-lookup"><span data-stu-id="008e7-129">TrimStart</span></span>

 <span data-ttu-id="008e7-130">**String.TrimStart** 메서드는 기존 문자열 개체의 시작 부분에서 문자를 제거하여 새 문자열을 만든다는 점을 제외하고 **String.TrimEnd** 메서드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-130">The **String.TrimStart** method is similar to the **String.TrimEnd** method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="008e7-131">문자 배열을 **TrimStart** 메서드에 전달하여 제거할 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-131">An array of characters is passed to the **TrimStart** method to specify the characters to be removed.</span></span> <span data-ttu-id="008e7-132">**TrimEnd** 메서드와 마찬가지로 문자 배열에서 요소의 순서는 트리밍 작업에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-132">As with the **TrimEnd** method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="008e7-133">배열에 지정되지 않은 문자가 발견되면 trim이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-133">The trim stops when a character not specified in the array is found.</span></span>  
  
 <span data-ttu-id="008e7-134">다음 예제에서는 문자열의 첫 번째 단어를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-134">The following example removes the first word of a string.</span></span> <span data-ttu-id="008e7-135">이 예제에서 배열에 있는 문자의 순서를 설명하기 위해 바뀐 `'l'` 문자 및 `'H'` 문자의 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-135">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#20)]
 [!code-csharp[Conceptual.String.BasicOps#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#20)]
 [!code-vb[Conceptual.String.BasicOps#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#20)]  
  
 <span data-ttu-id="008e7-136">이 코드는 콘솔에 `World!`를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-136">This code displays `World!` to the console.</span></span>  
  
## <a name="remove"></a><span data-ttu-id="008e7-137">제거</span><span class="sxs-lookup"><span data-stu-id="008e7-137">Remove</span></span>

 <span data-ttu-id="008e7-138"><xref:System.String.Remove%2A?displayProperty=nameWithType> 메서드는 기존 문자열의 지정된 위치에서 시작하는 지정된 수의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-138">The <xref:System.String.Remove%2A?displayProperty=nameWithType> method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="008e7-139">이 메서드에서는 0 기반 인덱스를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-139">This method assumes a zero-based index.</span></span>  
  
 <span data-ttu-id="008e7-140">다음 예제에서는 문자열의 0 기반 인덱스 중 5번째 위치에서 시작하는 문자열에서 10개의 문자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-140">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/trimming.cpp#21)]
 [!code-csharp[Conceptual.String.BasicOps#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/trimming.cs#21)]
 [!code-vb[Conceptual.String.BasicOps#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/trimming.vb#21)]  
  
## <a name="replace"></a><span data-ttu-id="008e7-141">Replace</span><span class="sxs-lookup"><span data-stu-id="008e7-141">Replace</span></span>

 <span data-ttu-id="008e7-142"><xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> 메서드를 호출하고 빈 문자열(<xref:System.String.Empty?displayProperty=nameWithType>)을 대체로 지정하여 문자열에서 지정된 문자나 부분 문자열을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-142">You can also remove a specified character or substring from a string by calling the <xref:System.String.Replace%28System.String%2CSystem.String%29?displayProperty=nameWithType> method and specifying an empty string (<xref:System.String.Empty?displayProperty=nameWithType>) as the replacement.</span></span> <span data-ttu-id="008e7-143">다음 예제에서는 문자열에서 모든 쉼표를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="008e7-143">The following example removes all commas from a string.</span></span>  
  
 [!code-csharp[Conceptual.String.BasicOps#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/replace1.cs#23)]
 [!code-vb[Conceptual.String.BasicOps#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/replace1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="008e7-144">참조</span><span class="sxs-lookup"><span data-stu-id="008e7-144">See also</span></span>

- [<span data-ttu-id="008e7-145">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="008e7-145">Basic String Operations</span></span>](basic-string-operations.md)
