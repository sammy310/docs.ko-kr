---
title: 모델 선언 함수
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: fb30dd86c29d6a7fff6f2c71d5fd892326e1fda4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147855"
---
# <a name="model-declared-function"></a>모델 선언 함수

*모델 선언 함수* 는 개념적 모델에 선언 된 함수 이지만 해당 개념적 모델에는 정의 되어 있지 않습니다. 호스팅 또는 스토리지 환경에서 함수를 정의할 수도 있습니다. 예를 들어, 모델 선언 함수를 데이터베이스에 정의된 함수에 매핑하여 개념적 모델에 서버 쪽 기능을 노출할 수 있습니다.  
  
 모델 선언 함수의 선언에는 다음 정보가 들어 있습니다.  
  
- 함수의 이름. (필수)  
  
- 반환 값의 형식 (선택 사항)  
  
    > [!NOTE]
    > 반환 값을 지정하지 않으면 반환 형식은 void입니다.  
  
- 매개 변수 이름과 형식을 포함하는 매개 변수 정보 (선택 사항)  
  
## <a name="example"></a>예제  

 [ADO.NET Entity Framework](./ef/index.md) 에서는[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(개념 스키마 정의 언어) 이라는 DSL (도메인별 언어)을 사용 하 여 개념적 모델을 정의 합니다. CSDL에서 모델 선언 함수의 한 가지 구현은 [FunctionImport 요소](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)를 사용 하는 함수 가져오기입니다. 다음 CSDL에서는 함수 가져오기 정의를 사용하여 엔터티 컨테이너를 정의합니다. 반환 형식을 지정하지 않았으므로 함수의 반환 형식은 void입니다.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 데이터 모델의 주요 개념](entity-data-model-key-concepts.md)
- [엔터티 데이터 모델](entity-data-model.md)
