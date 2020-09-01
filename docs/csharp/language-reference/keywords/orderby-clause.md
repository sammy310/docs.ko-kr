---
description: orderby 절 - C# 참조
title: orderby 절 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142351"
---
# <a name="orderby-clause-c-reference"></a>orderby 절(C# 참조)

쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 하위 시퀀스(그룹)가 오름차순이나 내림차순으로 정렬되도록 합니다. 하나 이상의 보조 정렬 작업을 수행하기 위해 여러 키를 지정할 수 있습니다. 정렬은 요소 형식에 대한 기본 비교자에 의해 수행됩니다. 기본 정렬 순서는 오름차순입니다. 사용자 지정 비교자를 지정할 수도 있습니다. 그러나 메서드 기반 구문을 통해서만 사용할 수 있습니다. 자세한 내용은 [데이터 정렬](../../programming-guide/concepts/linq/sorting-data.md)을 참조하세요.

## <a name="example"></a>예제

다음 예제에서 첫 번째 쿼리는 A부터 시작하여 사전순으로 단어를 정렬하고, 두 번째 쿼리는 동일한 단어를 내림차순으로 정렬합니다. `ascending` 키워드는 기본 정렬 값이며 생략할 수 있습니다.

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a>예제

다음 예제에서는 학생의 성을 기준으로 1차 정렬을 수행한 다음 이름을 기준으로 2차 정렬을 수행합니다.

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a>설명

컴파일 시간에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드 호출로 변환됩니다. `orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출로 변환됩니다.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [쿼리 키워드(LINQ)](query-keywords.md)
- [C#의 LINQ](../../linq/index.md)
- [group 절](group-clause.md)
- [LINQ(Language-Integrated Query)](../../programming-guide/concepts/linq/index.md)
