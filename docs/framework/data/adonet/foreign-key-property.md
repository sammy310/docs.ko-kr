---
title: 외래 키 속성
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: be0fcb94b0b457a33c17e7125cd22db50f298cc6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189320"
---
# <a name="foreign-key-property"></a>외래 키 속성

EDM (엔터티 데이터 모델)의 *외래 키 속성* 은 다른 엔터티 형식의 [엔터티 키](entity-key.md) 를 포함 하는 [엔터티 형식](entity-type.md) 에 대 한 기본 형식 [속성](property.md) (또는 기본 형식 속성 집합)입니다.  
  
 외래 키 속성은 관계형 데이터베이스의 외래 키 열과 유사합니다. 관계형 데이터베이스에서 외래 키 열을 사용 하 여 테이블의 행 간 관계를 만드는 것과 마찬가지로 개념적 모델의 외래 키 속성은 엔터티 형식 간의 [연결](association-type.md) 을 설정 하는 데 사용 됩니다. [참조 무결성 제약 조건은](referential-integrity-constraint.md) 형식 중 하나에 외래 키 속성이 있는 경우 두 엔터티 형식 간의 연결을 정의 하는 데 사용 됩니다.  
  
## <a name="example"></a>예제  

 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다. `Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "참조 제약 조건 모델 예")  
  
 [ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다. 다음 CSDL에서는 외래 키 속성 `PublisherId`를 사용하여 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 데이터 모델의 주요 개념](entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](entity-data-model.md)
