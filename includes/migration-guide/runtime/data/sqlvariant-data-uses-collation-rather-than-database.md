---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620289"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>Sql_variant 데이터는 데이터베이스 데이터 정렬 대신 sql_variant 데이터 정렬을 사용합니다.

#### <a name="details"></a>설명

<code>sql_variant</code> 데이터는 데이터베이스 데이터 정렬 대신 <code>sql_variant</code> 데이터 정렬을 사용합니다.

#### <a name="suggestion"></a>제안 해결 방법

이러한 변경을 통해 데이터베이스 데이터 정렬이 <code>sql_variant</code> 데이터 정렬과 다른 경우 데이터 손상 가능성을 해결합니다. 손상된 데이터를 사용하는 애플리케이션은 오류가 발생할 수 있습니다.

| 이름    | 값       |
|:--------|:------------|
| Scope   |투명|
|버전|4.5|
|형식|런타임|
