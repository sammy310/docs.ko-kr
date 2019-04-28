---
title: 열거형의 내부 형식 <typename>이(가) CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 636fcc36e7bac52467998dc9c59f14ba1bedead3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774883"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a>내부 형식 \<typename > 열거형의 CLS 규격이 아닙니다
이 열거형은 지정한 데이터 형식 부분을 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS). 이 아니므로 사용자 구성 요소에서 오류를 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 고 Visual Basic이 데이터 형식을 지원 합니다. 그러나 엄격 하 게 CLS 규격 코드 작성 하는 다른 구성 요소는이 데이터 형식은 지원 하지 않습니다. 이러한 구성 요소 구성 요소를 성공적으로 조작할 수 있습니다.  
  
 다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.  
  
- [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40032  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 구성 요소가 다른만 상호 작용 하는 경우 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 구성 요소 또는 다른 구성 요소와 인터페이스 하지, 아무 것도 변경할 필요가 없습니다.  
  
- 하지 않고 작성 된 구성 요소와 같이 하는 경우는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], 리플렉션을 통해를 확인할 수 있습니다 또는 설명서에서 지원 하는지 여부이 데이터 형식입니다. 이 경우 아무 것도 변경할 필요가 없습니다.  
  
- 이 데이터 형식은 지원 하지 않는 구성 요소와 같이 하는 경우에 가장 가까운 CLS 규격 형식으로 대체 해야 있습니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
- 자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다. 예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소는 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 Visual Basic 코드에서.  
  
## <a name="see-also"></a>참고자료

- [리플렉션(Visual Basic)](../../programming-guide/concepts/reflection.md)
- [리플렉션](../../../framework/reflection-and-codedom/reflection.md)
