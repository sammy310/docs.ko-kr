---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319550"
---
# <a name="navigate-entity-sql"></a>NAVIGATE (Entity SQL)

엔터티 사이에 설정된 관계를 탐색합니다.

## <a name="syntax"></a>구문

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a>인수

엔터티 인스턴스를 `instance-expression` 합니다.

CSDL (개념 스키마 정의 언어) 파일에서 관계의 형식 이름을 `relationship-type` 합니다. @No__t_0은 \<namespace >으로 한정 됩니다. \<relationship 형식 이름 >입니다.

관계의 끝을 `to` 합니다.

관계의 시작 부분을 `from` 합니다.

## <a name="return-value"></a>반환 값

끝 End의 카디널리티가 1인 경우 반환 값은 `Ref<T>`이고, 끝 End의 카디널리티가 n인 경우 반환 값은 `Collection<Ref<T>>`입니다.

## <a name="remarks"></a>주의

관계는 EDM (엔터티 데이터 모델)의 첫 번째 클래스 구문입니다. 둘 이상의 엔터티 형식 간에 관계를 설정할 수 있으며 사용자는 한쪽(엔터티)에서 다른 쪽으로 관계를 탐색할 수 있습니다. `from` 및 `to` 는 관계 내의 이름 확인에 모호성이 없는 경우에 한해 조건부로 사용 가능합니다.

NAVIGATE는 O 및 C 공간에서 유효합니다.

탐색 구문의 일반적인 형태는 다음과 같습니다.

navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )

예를 들면,

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

여기서 OrderCustomer는 `relationship`이고, Customer와 Order는 각각 관계의 `to-end` (고객)와 `from-end` (주문)입니다. OrderCustomer가 n:1 관계 이면 탐색 식의 결과 형식은 Ref \<Customer >입니다.

이 식이 좀 더 단순화된 형태는 다음과 같습니다.

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

마찬가지로, 다음 폼의 쿼리에서 navigate 식은 > > < 참조 \<Order 컬렉션을 생성 합니다.

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

인스턴스 식은 엔터티/참조 형식이어야 합니다.

## <a name="example"></a>예제

다음 Entity SQL 쿼리는 NAVIGATE 연산자를 사용하여 Address 및 SalesOrderHeader 엔터티 형식 사이에 설정된 관계를 탐색합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.

1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.

2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
- [방법: Navigate 연산자로 관계 탐색](navigate-entity-sql.md)
