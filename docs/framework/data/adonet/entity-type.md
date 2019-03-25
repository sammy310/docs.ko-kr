---
title: 엔터티 형식(entity type)
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: cb542a1750a6b45dd2fca4d32501719470d9a78a
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410890"
---
# <a name="entity-type"></a>엔터티 형식(entity type)
합니다 *엔터티 형식* 엔터티 데이터 모델 (EDM)를 사용 하 여 데이터의 구조를 설명 하기 위한 기본적인 빌딩 블록입니다. 개념적 모델에서 엔터티 형식은 고객이나 주문과 같은 최상위 개념의 구조를 나타냅니다. 엔터티 형식은 엔터티 형식 인스턴스의 템플릿입니다. 각 템플릿에는 다음 정보가 들어 있습니다.  
  
-   고유한 이름 (필수)  
  
-   [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 하나 이상의 속성으로 정의 합니다. (필수)  
  
-   데이터의 형태로 [속성](../../../../docs/framework/data/adonet/property.md)합니다. 필요에 따라  
  
-   [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 간에 탐색할 수 있도록 [끝](../../../../docs/framework/data/adonet/association-end.md) 의 [연결](../../../../docs/framework/data/adonet/association-type.md) 다른 end로 합니다. 이 매개 변수는 선택 사항입니다.  
  
 응용 프로그램에서 엔터티 형식의 인스턴스는 특정 고객 또는 주문과 같은 특정 개체를 나타냅니다. 엔터티 형식의 각 인스턴스는 고유 해야 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 안에 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md)합니다.  
  
 두 엔터티 형식 인스턴스는 형식이 동일하고 해당 엔터티 키 값이 동일한 경우에만 동일한 것으로 간주됩니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/entity-type/example-model-three-entity-types.gif)  
  
 엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.  
  
 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 (DSL)를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>참고자료
- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facet](../../../../docs/framework/data/adonet/facet.md)
