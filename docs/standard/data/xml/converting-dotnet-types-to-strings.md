---
title: .NET 형식을 문자열로 변환
ms.date: 03/30/2017
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: 9744224b4346b865a112b0eb6957f12553e1ec5f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830989"
---
# <a name="convert-net-types-to-strings"></a>.NET 형식을 문자열로 변환

.NET 형식을 문자열로 변환하려면 **ToString** 메서드를 사용합니다. **ToString** 메서드는 전달된 형식의 문자열 표현을 반환합니다. 다음 표에서는 XSD(XML 스키마) 사양에 대응하는 형식으로 문자열을 반환하는 .NET 형식의 목록을 보여 줍니다.  
  
|.NET 형식|반환된 문자열 형식|  
|-------------------------|--------------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|형식은 "yyyy-MM-ddTHH:mm:sszzzzzz" 및 해당 하위 집합입니다.|  
|Timespan|형식은 PnYnMnTnHnMnS입니다. 예를 들어, `P2Y10M15DT10H30M20S`는 2년 10개월 15일 10시간 30분 20초의 지속 시간을 나타냅니다.|  
  
## <a name="see-also"></a>참조

- [XML 데이터 형식 변환](conversion-of-xml-data-types.md)
- [문자열을 .NET 데이터 형식으로 변환](converting-strings-to-dotnet-data-types.md)
