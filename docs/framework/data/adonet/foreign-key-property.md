---
title: 외래 키 속성
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: 8680019f6f1a53233b5c49163f474cf33409b69b
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2019
ms.locfileid: "57674473"
---
# <a name="foreign-key-property"></a>외래 키 속성
A *외래 키 속성* 엔터티 데이터 모델 (EDM)의 기본 형식인 [속성](../../../../docs/framework/data/adonet/property.md) (또는 기본 형식 속성 집합)에 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 를포함하는[엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 다른 엔터티 형식입니다.  
  
 외래 키 속성은 관계형 데이터베이스의 외래 키 열과 유사합니다. 테이블의 행 간의 관계를 만들려면 관계형 데이터베이스의 외래 키 열을 사용 된 동일한 방식으로 개념적 모델에서 외래 키 속성을 설정 하 되 [연결](../../../../docs/framework/data/adonet/association-type.md) 엔터티 형식 간의 합니다. A [참조 무결성 제약 조건](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) 형식 중 하나에 외래 키 속성이 경우 두 엔터티 형식 간의 연결을 정의 하는 데 사용 됩니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다. 
  `Book` 엔터티 형식에는 `PublisherId` 연결에 참조 무결성 제약 조건을 정의할 때 `Publisher` 엔터티 형식의 엔터티 키를 참조하는 `PublishedBy` 속성이 있습니다.  
  
 ![RefConstraintModel](./media/foreign-key-property/reference-constraint-model.gif "참조 제약 조건이 모델의 예")  
  
 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 외래 키 속성 `PublisherId`를 사용하여 위의 개념적 모델에 표시된 `PublishedBy` 연결에 참조 무결성 제약 조건을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>참고자료
- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
