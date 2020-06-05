---
title: 속성과 변수의 차이점
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: 162bd71eaebdf55f6be89e0c5dce7acc1b975d79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403306"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Visual Basic에서 속성과 변수의 차이점
변수와 속성은 모두 액세스할 수 있는 값을 나타냅니다. 그러나 저장소와 구현에는 차이점이 있습니다.  
  
## <a name="variables"></a>variables  
 *변수* 는 메모리 위치에 직접 대응 됩니다. 단일 선언문을 사용 하 여 변수를 정의 합니다. 변수는 프로시저 내에 정의 되 고 해당 프로시저 내 에서만 사용할 수 있는 *지역 변수*이거나 모듈, 클래스 또는 구조에 정의 되어 있지만 프로시저 내에서 정의 되지 않은 *멤버 변수일*수 있습니다. 멤버 변수는 *필드*라고도 합니다.  
  
## <a name="properties"></a>속성  
 *속성* 은 모듈, 클래스 또는 구조에 정의 된 데이터 요소입니다. 및 문 사이에 코드 블록을 사용 하 여 속성을 정의 `Property` `End Property` 합니다. 코드 블록은 `Get` 프로시저, `Set` 프로시저 또는 둘 다를 포함 합니다. 이러한 프로시저를 *속성 프로시저* 또는 *속성 접근자*라고 합니다. 속성의 값을 검색 하거나 저장 하는 것 외에도 액세스 카운터를 업데이트 하는 등의 사용자 지정 작업을 수행할 수 있습니다.  
  
## <a name="differences"></a>차이점  
 다음 표에서는 변수와 속성의 몇 가지 중요 한 차이점을 보여 줍니다.  
  
|차이 가리키기|변수|속성|  
|-------------------------|--------------|--------------|  
|선언|단일 선언문|코드 블록의 일련 문|  
|구현|단일 저장소 위치|실행 코드 (속성 프로시저)|  
|스토리지|변수의 값에 직접 연결|일반적으로 내부 저장소는 속성의 포함 하는 클래스 또는 모듈 외부에서 사용할 수 없습니다.<br /><br /> 속성의 값이 저장 된 요소로 있을 수도 있고 없을 수도 있습니다. <sup>1</sup>|  
|실행 코드|없음|하나 이상의 프로시저가 있어야 합니다.|  
|읽기 및 쓰기 권한|읽기/쓰기 또는 읽기 전용|읽기/쓰기, 읽기 전용 또는 쓰기 전용|  
|사용자 지정 작업 (값을 허용 하거나 반환 하는 것 외에)|가능하지 않음|속성 값을 설정 하거나 검색 하는 과정에서 수행할 수 있습니다.|  
  
 <sup>1</sup> 변수와 달리 속성의 값은 저장소의 단일 항목에 직접적으로 해당 하지 않을 수 있습니다. 저장소는 편리 하거나 보안을 위해 여러 조각으로 분할 될 수 있으며, 값은 암호화 된 형식으로 저장 될 수 있습니다. 이러한 경우 프로시저는 `Get` 조각을 조합 하거나 저장 된 값의 암호를 해독 하 고 `Set` 새 값을 암호화 하거나이를 구성 저장소로 분할 합니다. 속성 값은 하루와 같이 임시 일 수 있으며, `Get` 이 경우 프로시저는 속성에 액세스할 때마다 즉석에서이를 계산 합니다.  
  
## <a name="see-also"></a>참고 항목

- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Dim 문](../../../language-reference/statements/dim-statement.md)
- [방법: 속성 만들기](./how-to-create-a-property.md)
- [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)
- [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](./how-to-declare-and-call-a-default-property.md)
- [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
- [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
