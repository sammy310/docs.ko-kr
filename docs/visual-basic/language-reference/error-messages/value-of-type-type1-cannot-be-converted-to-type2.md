---
title: "'type1' 형식의 값을 'type2'(으)로 변환할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870237"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>'type1' 형식의 값을 'type2'(으)로 변환할 수 없습니다.

' Type1 ' 형식의 값을 ' type2 ' (으)로 변환할 수 없습니다. ' Value ' 속성을 사용 하 여 ' '의 첫 번째 요소에 대 한 문자열 값을 가져올 수 있습니다 \<parentElement> .  
  
 XML 리터럴을 특정 형식으로 암시적으로 캐스팅하려고 했습니다. XML 리터럴은 지정된 형식으로 암시적으로 캐스팅할 수 없습니다.  
  
 **오류 ID:** BC31194  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- XML 리터럴의 `Value` 속성을 사용하여 해당 값을 `String`으로 참조합니다. `CType` 함수, 다른 형식 변환 함수 또는 <xref:System.Convert> 클래스를 사용하여 지정된 형식으로 값을 캐스팅합니다.  
  
## <a name="see-also"></a>참조

- <xref:System.Convert>
- [형식 변환 함수](../functions/type-conversion-functions.md)
- [XML 리터럴](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
