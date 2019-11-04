---
title: 수량자 작업(C#)
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: 5899af79799d5b8404e60027d7ba1b005c4b1b79
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423357"
---
# <a name="quantifier-operations-c"></a>수량자 작업(C#)
수량자 작업은 시퀀스에서 조건을 충족하는 요소가 일부인지 전체인지를 나타내는 <xref:System.Boolean> 값을 반환합니다.  
  
 다음 그림은 두 개의 서로 다른 소스 시퀀스에 대한 두 개의 서로 다른 수량자 작업을 보여 줍니다. 첫 번째 작업은 요소 중 하나 이상이 문자 'A'이고 결과가 `true`인지 묻습니다. 두 번째 작업은 모든 요소가 문자 'A'이고 결과가 `true`인지 묻습니다.  
  
 ![LINQ 수량자 작업](./media/quantifier-operations/linq-quantifier-operations.png)  
  
 다음 섹션에는 수량자 작업을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|C# 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|---------------------------------|----------------------|  
|모두|시퀀스의 모든 요소가 조건을 만족하는지를 확인합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.All%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.All%2A?displayProperty=nameWithType>|  
|임의의 값|시퀀스의 임의의 요소가 조건을 만족하는지를 확인합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Any%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Any%2A?displayProperty=nameWithType>|  
|포함|시퀀스에 지정된 요소가 들어 있는지를 확인합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Contains%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Contains%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(C#)](./standard-query-operators-overview.md)
- [방법: 런타임에 동적으로 조건자 필터 지정](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [방법: 지정된 단어 집합이 들어 있는 문장 쿼리(LINQ)(C#)](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
