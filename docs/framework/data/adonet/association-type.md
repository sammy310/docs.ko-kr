---
title: 연결 형식
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 6f6eb91d4f292c7e98b8c9a1d814ed6bf71b7370
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198758"
---
# <a name="association-type"></a>연결 형식

연결 *형식* (연결이 라고도 함)은 EDM (엔터티 데이터 모델)에서 관계를 설명 하는 기본 구성 요소입니다. 개념적 모델에서 연결은 두 [엔터티 형식](entity-type.md) (예: 및) 간의 관계를 나타냅니다 `Customer` `Order` . 애플리케이션에서 연결 인스턴스는 특정 연결(예: `Customer` 인스턴스와 `Order` 인스턴스 간의 연결)을 나타냅니다. 연결 인스턴스는 [연결 집합](association-set.md)에 논리적으로 그룹화 됩니다.  
  
 연결 정의에는 다음 정보가 들어 있습니다.  
  
- 고유한 이름 (필수)  
  
- 관계의 각 엔터티 형식에 대해 하나씩, 두 개의 [연결 끝](association-end.md)입니다. (필수)  
  
    > [!NOTE]
    > 연결은 셋 이상 엔터티 형식 간의 관계를 나타낼 수 없습니다. 그러나 연결은 각 연결 End에 같은 엔터티 형식을 지정하여 자체 관계를 정의할 수 있습니다.  
  
- [참조 무결성 제약 조건](referential-integrity-constraint.md)입니다. (선택 사항)  
  
 각 연결 end는 연결의 한쪽 끝에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는 [연결 end 복합성](association-end-multiplicity.md) 을 지정 해야 합니다. 연결 end 복합성은 1 (1), 0 또는 1 (0 ..1) 또는 다 수 ()의 값을 가질 수 있습니다 \* . 연결의 한 end에 있는 엔터티 형식 인스턴스는 엔터티 형식에서 노출 된 경우 [탐색 속성](navigation-property.md) 또는 외래 키를 통해 액세스할 수 있습니다. 자세한 내용은 [엔터티 데이터 모델: 외래 키](foreign-key-property.md)를 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다. `PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다. 끝의 복합성은 `Publisher` 1이 고, 끝의 복합성은 `Book` 다 수 ()입니다. 즉 \* , 게시자가 많은 책을 게시 하 고 한 출판사에서 책을 게시 함을 나타냅니다.  
  
 ![세 개의 엔터티 형식이 있는 예제 모델](./media/association-type/example-model-three-entity-types.gif)  
  
 [ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 데이터 모델의 주요 개념](entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](entity-data-model.md)
