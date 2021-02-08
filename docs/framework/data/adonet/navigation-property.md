---
description: '자세히 알아보기: 탐색 속성'
title: 탐색 속성
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: 4655c8ef1b18972697e41fa1c7c6185945335aa1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786240"
---
# <a name="navigation-property"></a>탐색 속성

*탐색 속성* 은 [연결](association-type.md) 의 한 [end](association-end.md) 에서 다른 end로의 탐색을 허용 하는 [엔터티 형식의](entity-type.md) 선택적 속성입니다. 다른 [속성과](property.md)달리 탐색 속성은 데이터를 전달 하지 않습니다.

탐색 속성 정의에는 다음 정보가 들어 있습니다.

- 이름 (필수)

- 탐색하는 연결 (필수)

- 탐색하는 연결의 End (필수)

탐색 속성은 연결의 end에 있는 두 엔터티 형식에서 모두 선택 사항입니다. 연결의 End에 있는 한 엔터티 형식에 대해 탐색 속성을 정의하는 경우 연결의 다른 End에 있는 엔터티 형식에 대해서는 탐색 속성을 정의할 필요가 없습니다.

탐색 속성의 데이터 형식은 해당 원격 [연결 end](association-end.md)의 [복합성](association-end-multiplicity.md) 에 의해 결정 됩니다. 예를 들어, `OrdersNavProp` 탐색 속성이 `Customer` 엔터티 형식에 존재하며 `Customer`와 `Order` 간의 일대다 연결을 탐색한다고 가정합니다. 탐색 속성에 대 한 원격 연결 end의 복합성은 다 수 ( \* ) 이므로 해당 데이터 형식은의 컬렉션입니다 `Order` . 마찬가지로 `CustomerNavProp` 탐색 속성이 `Order` 엔터티 형식에 존재하는 경우 원격 End의 복합성이 한 개(1)이므로 해당 데이터 형식은 `Customer`가 됩니다.

## <a name="example"></a>예제

다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다. 탐색 속성 `Publisher` 및는 `Authors` Book 엔터티 형식에 정의 됩니다. 탐색 속성 `Books`는 Publisher 엔터티 형식과 `Author` 엔터티 형식에 모두 정의됩니다.

![세 개의 엔터티 형식이 포함 된 개념적 모델을 보여 주는 다이어그램](./media/navigation-property/conceptual-model-entity-types-associations.gif)  

[ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.

[!code-xml[EDM_Example_Model#EntityExample](~/samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]

XML 특성은 탐색 속성을 정의 하는 데 필요한 정보를 전달 하는 데 사용 됩니다. 특성은 `Name` 속성의 이름을 포함 하 고, 탐색 `Relationship` 하는 연결의 이름을 포함 하 고, `FromRole` `ToRole` 연결의 끝을 포함 합니다.

## <a name="see-also"></a>참고 항목

- [엔터티 데이터 모델의 주요 개념](entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](entity-data-model.md)
- [관계, 탐색 속성 및 외래 키](/ef/ef6/fundamentals/relationships)
