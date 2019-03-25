---
title: 연결 집합 End
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: 61dc00e6c349a25767f6221bed56ef8b65f823d9
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412008"
---
# <a name="association-set-end"></a>연결 집합 End
*연결 집합 end* 하 게 식별 하는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 하며 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 끝에 [연결 집합](../../../../docs/framework/data/adonet/association-set.md). 연결 집합 End는 연결 집합의 일부로 정의되고 연결 집합에는 정확히 두 개의 연결 집합 End가 있어야 합니다.  
  
 연결 집합 End 정의에는 다음 정보가 들어 있습니다.  
  
-   연결 집합과 관련된 엔터티 형식 중 하나 (필수)  
  
-   연결 집합과 관련된 엔터티 형식에 대한 엔터티 집합 (필수)  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.  
  
 ![세 가지 엔터티 형식을 사용 하 여 예제 모델](./media/association-set-end/example-model-three-entity-types.gif)  
  
 다음 다이어그램에서는 위에 나온 개념적 모델을 기반으로 하여 하나의 연결 집합(`PublishedBy`) 및 두 개의 엔터티 집합(`Books` 및 `Publishers`)을 보여 줍니다. 연결 집합 End는 `Books` 및 `Publishers` 엔터티 집합입니다. bi 합니다 `Books` 엔터티 집합의 인스턴스를 나타냅니다는 `Book` 런타임에 엔터티 형식입니다. 마찬가지로 Pj 나타냅니다는 `Publisher` 인스턴스에 `Publishers` 엔터티 집합입니다. BiPj의 인스턴스를 나타냅니다 합니다 `PublishedBy` 의 연결을 `PublishedBy` 연결 집합입니다.  
  
 ![집합 예제를 보여 주는 스크린샷.](./media/association-set-end/sets-example-association.gif)  
  
 합니다 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어 이라고 하는 DSL을 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다. 연결 집합 End는 각 연결 집합 정의의 일부로 정의되어 있습니다.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>참고자료
- [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
