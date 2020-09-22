---
title: "'<propertyname>' 속성이 일부 코드 경로에 대해서만 값을 반환합니다."
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 6a80a8275a7b9c5e3cbfa410ee219e0d16ce5918
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870950"
---
# <a name="property-propertyname-doesnt-return-a-value-on-all-code-paths"></a>'\<propertyname>' 속성이 일부 코드 경로에 대해서만 값을 반환합니다.

' \<propertyname> ' 속성이 일부 코드 경로에 대해서만 값을 반환 합니다. 이 결과를 사용하면 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 속성 `Get` 프로시저의 코드를 통해 값을 반환 하지 않는 경로가 하나 이상 있습니다.  
  
 다음 방법 중 하나를 통해 속성 프로시저에서 값을 반환할 수 있습니다 `Get` .  
  
- 속성 이름에 값을 할당 한 다음 `Exit Property` 문을 수행 합니다.  
  
- 속성 이름에 값을 할당 한 다음 `End Get` 문을 수행 합니다.  
  
- [반환 문에](../statements/return-statement.md)값을 포함 합니다.  
  
 컨트롤이 또는로 전달 `Exit Property` `End Get` 되 고 속성 이름에 값을 할당 하지 않은 경우 `Get` 프로시저는 속성 데이터 형식의 기본값을 반환 합니다. 자세한 내용은 [함수 문의](../statements/function-statement.md)"Behavior"를 참조 하십시오.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC42107  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 제어 흐름 논리를 확인 하 고 반환을 발생 시키는 모든 문 앞에 값을 할당 해야 합니다.  
  
     항상 문을 사용 하는 경우 프로시저의 모든 반환에서 값을 반환 하도록 보장 하는 것이 더 쉽습니다 `Return` . 이 작업을 수행 하는 경우 앞의 마지막 문이 문 이어야 합니다 `End Get` `Return` .  
  
## <a name="see-also"></a>참조

- [속성 프로시저](../../programming-guide/language-features/procedures/property-procedures.md)
- [Property Statement](../statements/property-statement.md)
- [Get 문](../statements/get-statement.md)
