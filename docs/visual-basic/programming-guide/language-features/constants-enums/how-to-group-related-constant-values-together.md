---
description: '자세한 정보: 방법: 관련 상수 값 그룹화 (Visual Basic)'
title: '방법: 관련 상수 값 그룹화'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: ddd60696d2c751810e49ecbcb537589bedc58abf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471593"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>방법: 관련 상수 값 그룹화(Visual Basic)

열거형은 관련 상수를 함께 그룹화 하는 가장 좋은 방법입니다. `Enum`클래스 또는 모듈의 선언 섹션에 문을 사용 하 여 열거형을 만듭니다. 자세한 내용은 [방법: 열거형 선언](how-to-declare-enumerations.md)을 참조 하세요.  
  
### <a name="to-group-related-constant-values"></a>관련 상수 값을 그룹화 하려면  
  
1. 코드 액세스 수준, `Enum` 키워드 및 올바른 이름을 포함 하는 선언을 작성 합니다. 이 예제에서는 `Private` 열거형을 만듭니다 `temperatureValues` .  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. 열거형에서 상수를 정의 합니다. 이 예제에서는 열거형을 만들고 `Public` `temperatureValues` 해당 값을 할당 합니다.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>추가 정보

- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md)
- [열거형을 사용하는 경우](when-to-use-an-enumeration.md)
- [상수 개요](constants-overview.md)
- [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)
- [상수 및 열거형](../../../language-reference/constants-and-enumerations.md)
