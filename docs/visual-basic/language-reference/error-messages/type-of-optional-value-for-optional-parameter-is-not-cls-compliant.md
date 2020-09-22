---
title: 선택적 매개 변수 <parametername>에 대한 선택적 값의 형식이 CLS 규격이 아닙니다.
ms.date: 07/20/2015
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords:
- BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
ms.openlocfilehash: 77d23fff518cb3b0768264ddd07728e3ad6b9f91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872213"
---
# <a name="type-of-optional-value-for-optional-parameter-parametername-is-not-cls-compliant"></a>선택적 매개 변수 \<parametername>에 대한 선택적 값의 형식이 CLS 규격이 아닙니다.

프로시저는 `<CLSCompliant(True)>`로 표시되지만 비규격 형식의 기본값을 가진 [선택적](../modifiers/optional.md) 매개 변수를 선언합니다.  
  
 프로시저가 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다. 이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다. 또한 선택적 매개 변수의 기본값에도 적용됩니다.  
  
 다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.  
  
- [SByte 데이터 형식](../data-types/sbyte-data-type.md)  
  
- [UInteger 데이터 형식](../data-types/uinteger-data-type.md)  
  
- [ULong 데이터 형식](../data-types/ulong-data-type.md)  
  
- [UShort 데이터 형식](../data-types/ushort-data-type.md)  
  
 <xref:System.CLSCompliantAttribute> 특성을 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.  
  
 **오류 ID:** BC40042  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 선택적 매개 변수에이 특정 형식의 기본값이 있어야 하는 경우를 제거 <xref:System.CLSCompliantAttribute> 합니다. 프로시저는 CLS 규격일 수 없습니다.  
  
- 프로시저가 CLS 규격이어야 하는 경우 이 기본값의 형식을 가장 가까운 CLS 규격 형식으로 변경합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.  
  
- Automation 또는 COM 개체와 상호 작용 하는 경우 일부 형식의 데이터 너비가 .NET Framework에 비해 다릅니다. 예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소에서 16 비트 정수를 허용 하는 경우 `Short` `Integer` 관리 되는 Visual Basic 코드에서 대신로 선언 합니다.
