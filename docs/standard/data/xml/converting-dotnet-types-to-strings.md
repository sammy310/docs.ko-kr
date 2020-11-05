---
title: .NET 형식을 문자열로 변환
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: ca35af17a402dc901c02edf94099af1377e1160f
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687623"
---
# <a name="convert-net-types-to-strings"></a><span data-ttu-id="9a9b8-102">.NET 형식을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="9a9b8-102">Convert .NET types to strings</span></span>

<span data-ttu-id="9a9b8-103">.NET 형식을 문자열로 변환하려면 **ToString** 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-103">If you want to convert a .NET type to a string, use the **ToString** method.</span></span> <span data-ttu-id="9a9b8-104">**ToString** 메서드는 전달된 형식의 문자열 표현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-104">The **ToString** method returns a string representation of the type passed in.</span></span> <span data-ttu-id="9a9b8-105">다음 표에서는 XSD(XML 스키마) 사양에 대응하는 형식으로 문자열을 반환하는 .NET 형식의 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-105">The following table lists the .NET types that return a string in a format that maps to the XML Schema (XSD) specifications.</span></span>  
  
|<span data-ttu-id="9a9b8-106">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="9a9b8-106">.NET type</span></span>|<span data-ttu-id="9a9b8-107">반환된 문자열 형식</span><span class="sxs-lookup"><span data-stu-id="9a9b8-107">String type returned</span></span>|  
|-------------------------|--------------------------|  
|<span data-ttu-id="9a9b8-108">Boolean</span><span class="sxs-lookup"><span data-stu-id="9a9b8-108">Boolean</span></span>|<span data-ttu-id="9a9b8-109">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="9a9b8-109">"true", "false"</span></span>|  
|<span data-ttu-id="9a9b8-110">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="9a9b8-110">Single.PositiveInfinity</span></span>|<span data-ttu-id="9a9b8-111">"INF"</span><span class="sxs-lookup"><span data-stu-id="9a9b8-111">"INF"</span></span>|  
|<span data-ttu-id="9a9b8-112">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="9a9b8-112">Single.NegativeInfinity</span></span>|<span data-ttu-id="9a9b8-113">"-INF"</span><span class="sxs-lookup"><span data-stu-id="9a9b8-113">"-INF"</span></span>|  
|<span data-ttu-id="9a9b8-114">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="9a9b8-114">Double.PositiveInfinity</span></span>|<span data-ttu-id="9a9b8-115">"INF"</span><span class="sxs-lookup"><span data-stu-id="9a9b8-115">"INF"</span></span>|  
|<span data-ttu-id="9a9b8-116">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="9a9b8-116">Double.NegativeInfinity</span></span>|<span data-ttu-id="9a9b8-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="9a9b8-117">"-INF"</span></span>|  
|<span data-ttu-id="9a9b8-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="9a9b8-118">DateTime</span></span>|<span data-ttu-id="9a9b8-119">형식은 "yyyy-MM-ddTHH:mm:sszzzzzz" 및 해당 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-119">Format is yyyy-MM-ddTHH:mm:sszzzzzz and its subsets.</span></span>|  
|<span data-ttu-id="9a9b8-120">Timespan</span><span class="sxs-lookup"><span data-stu-id="9a9b8-120">Timespan</span></span>|<span data-ttu-id="9a9b8-121">형식은 PnYnMnTnHnMnS입니다. 예를 들어, `P2Y10M15DT10H30M20S`는 2년 10개월 15일 10시간 30분 20초의 지속 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a9b8-121">Format is PnYnMnTnHnMnS, for example, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10hours, 30 minutes and 20 seconds.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a9b8-122">참조</span><span class="sxs-lookup"><span data-stu-id="9a9b8-122">See also</span></span>

- [<span data-ttu-id="9a9b8-123">XML 데이터 형식 변환</span><span class="sxs-lookup"><span data-stu-id="9a9b8-123">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="9a9b8-124">문자열을 .NET 데이터 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="9a9b8-124">Converting Strings to .NET Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
