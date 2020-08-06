---
title: 수량자 작업(C#)
description: 수량자 작업에 대해 알아봅니다. 이러한 작업은 시퀀스에서 일부 또는 모든 요소가 조건을 만족하는지 여부를 나타내는 부울 값을 반환합니다.
ms.date: 07/20/2015
ms.assetid: 84ac2ac2-7a63-4581-bc4c-14e34be1493b
ms.openlocfilehash: ce06f887d3ad7b10cbdedf9e33072df2c0819ef1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299151"
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

## <a name="query-expression-syntax-examples"></a>쿼리 식 구문 예제  
  
### <a name="all"></a>모두  
다음 예제에서는 `All`을 사용하여 모든 문자열이 특정 길이인지 확인합니다.
  
[!code-csharp[All](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#All)]  
  
### <a name="any"></a>임의의 값  
다음 예제에서는 `Any`를 사용하여 모든 문자열이 'o'로 시작하는지 확인합니다.  
  
[!code-csharp[Any](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Any)]  
  
### <a name="contains"></a>포함  
다음 예제에서는 `Contains`를 사용하여 배열에 특정 요소가 있는지 확인합니다.  
  
[!code-csharp[Contains](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQQuantifier/CS/Quantifier.cs#Contains)]  
  
## <a name="see-also"></a>참조

- <xref:System.Linq>
- [표준 쿼리 연산자 개요(C#)](./standard-query-operators-overview.md)
- [런타임에 동적으로 조건자 필터 지정](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
- [지정된 단어 집합이 들어 있는 문장을 쿼리하는 방법(LINQ)(C#)](./how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq.md)
