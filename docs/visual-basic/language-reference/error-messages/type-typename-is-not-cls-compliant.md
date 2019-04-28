---
title: <typename>' 형식이 CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764376"
---
# <a name="type-typename-is-not-cls-compliant"></a>형식 \<typename > CLS 규격이 아님
변수, 속성 또는 함수 반환 CLS와 호환 되지 않는 데이터 형식으로 선언 됩니다.  
  
 과 호환 되도록 응용 프로그램을 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS) CLS 규격 형식만 사용 해야 합니다.  
  
 다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.  
  
- [SByte 데이터 형식](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger 데이터 형식](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong 데이터 형식](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort 데이터 형식](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **오류 ID:** BC40041  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- CLS와 호환 되도록 응용 프로그램에 필요한 경우이 요소의 데이터 형식을 가장 가까운 CLS 규격 형식으로 변경 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
- 응용 프로그램에 CLS 규격이 될 필요가 없는 경우 아무 것도 변경할 필요가 없습니다. 하지만 해야 해당 비 호환성 인식 합니다.