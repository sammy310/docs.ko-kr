---
title: .NET에서 문자열 채우기
description: .NET에서 문자열을 패딩하는 방법을 알아봅니다. String.PadLeft 및 String.PadRight 메서드를 사용하여 선행 또는 후행 문자를 추가해 지정된 총 길이를 달성합니다.
ms.date: 03/15/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
ms.openlocfilehash: 9931db1e76e3737ab3803400928169b30c3ecbda
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822947"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="34425-104">.NET에서 문자열 채우기</span><span class="sxs-lookup"><span data-stu-id="34425-104">Padding Strings in .NET</span></span>

<span data-ttu-id="34425-105">다음 <xref:System.String> 메서드 중 하나를 사용하여 원래 문자열에 선행 또는 후행 문자를 지정된 총 길이까지 추가해 새로 구성된 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34425-105">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="34425-106">안쪽 여백 문자는 공백이나 지정된 문자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34425-106">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="34425-107">결과 문자열은 오른쪽 맞춤 또는 왼쪽 맞춤으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="34425-107">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="34425-108">원래 문자열의 길이가 원하는 총 길이보다 크거나 같은 경우 안쪽 여백 메서드는 변경되지 않은 원래 문자열을 반환합니다. 자세한 내용은 <xref:System.String.PadLeft%2A?displayProperty=nameWithType> 및 <xref:System.String.PadRight%2A?displayProperty=nameWithType> 메서드의 두 오버로드의 **반환** 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34425-108">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="34425-109">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="34425-109">Method name</span></span>|<span data-ttu-id="34425-110">기능</span><span class="sxs-lookup"><span data-stu-id="34425-110">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="34425-111">선행 문자로 문자열의 지정한 총 길이를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="34425-111">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="34425-112">후행 문자로 문자열의 지정한 총 길이를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="34425-112">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="34425-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="34425-113">PadLeft</span></span>  
 <span data-ttu-id="34425-114"><xref:System.String.PadLeft%2A?displayProperty=nameWithType> 메서드는 지정된 총 길이에 맞도록 필요한 만큼 선행 채움 문자를 원래 문자열에 연결하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34425-114">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="34425-115"><xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> 메서드는 공백을 채움 문자로 사용하며, <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 메서드를 사용하면 고유한 채움 문자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34425-115">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="34425-116">다음 코드 예제에서는 <xref:System.String.PadLeft%2A> 메서드를 사용하여 20자 길이의 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34425-116">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="34425-117">이 예제에서는 콘솔에 "`--------Hello World!`"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="34425-117">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="34425-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="34425-118">PadRight</span></span>  
 <span data-ttu-id="34425-119"><xref:System.String.PadRight%2A?displayProperty=nameWithType> 메서드는 지정된 총 길이에 맞도록 필요한 만큼 후행 채움 문자를 원래 문자열에 연결하여 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34425-119">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="34425-120"><xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> 메서드는 공백을 채움 문자로 사용하며, <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> 메서드를 사용하면 고유한 채움 문자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34425-120">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="34425-121">다음 코드 예제에서는 <xref:System.String.PadRight%2A> 메서드를 사용하여 20자 길이의 새 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="34425-121">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="34425-122">이 예제에서는 콘솔에 "`Hello World!--------`"를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="34425-122">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="34425-123">참조</span><span class="sxs-lookup"><span data-stu-id="34425-123">See also</span></span>

- [<span data-ttu-id="34425-124">기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="34425-124">Basic String Operations</span></span>](basic-string-operations.md)
