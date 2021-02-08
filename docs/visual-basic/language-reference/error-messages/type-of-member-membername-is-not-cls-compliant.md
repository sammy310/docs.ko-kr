---
description: "자세한 정보: BC40025: ' ' 멤버의 형식이 <membername> CLS 규격이 아닙니다."
title: "'<membername>' 멤버의 형식이 CLS 규격이 아닙니다."
ms.date: 07/20/2015
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
ms.openlocfilehash: 4fe83999a0cb2d678ccc0119509a368160dfc3ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774878"
---
# <a name="bc40025-type-of-member-membername-is-not-cls-compliant"></a>BC40025: ' ' 멤버의 형식이 \<membername> CLS 규격이 아닙니다.

이 멤버에 대해 지정 된 데이터 형식은 [언어 독립성 및 Language-Independent 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS)의 일부가 아닙니다. .NET Framework 및 Visual Basic이 데이터 형식을 지원 하기 때문에이는 구성 요소 내에서 오류가 아닙니다. 그러나 엄격 하 게 CLS 규격 코드로 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않을 수 있습니다. 이러한 구성 요소는 구성 요소와 성공적으로 상호 작용 하지 못할 수 있습니다.

 다음 Visual Basic 데이터 형식은 CLS 규격이 아닙니다.

- [SByte 데이터 형식](../data-types/sbyte-data-type.md)

- [UInteger 데이터 형식](../data-types/uinteger-data-type.md)

- [ULong 데이터 형식](../data-types/ulong-data-type.md)

- [UShort 데이터 형식](../data-types/ushort-data-type.md)

 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.

 **오류 ID:** BC40025

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 구성 요소가 다른 .NET Framework 구성 요소에만 인터페이스 하거나 다른 구성 요소와 상호 작용 하지 않는 경우 아무 것도 변경할 필요가 없습니다.

- .NET Framework 용으로 작성 되지 않은 구성 요소와 상호 작용 하는 경우 리플렉션 또는 설명서에서이 데이터 형식을 지원 하는지 여부를 확인할 수 있습니다. 이 경우 아무것도 변경할 필요가 없습니다.

- 이 데이터 형식을 지원 하지 않는 구성 요소와 상호 작용 하는 경우 가장 가까운 CLS 규격 형식으로 바꾸어야 합니다. 예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다. 확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.

- Automation 또는 COM 개체와 상호 작용 하는 경우 일부 형식의 데이터 너비가 .NET Framework에 비해 다릅니다. 예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다. 이러한 구성 요소에 16 비트 인수를 전달 하는 경우 `UShort` `UInteger` 관리 되는 Visual Basic 코드에서 대신로 선언 합니다.

## <a name="see-also"></a>참조

- [리플렉션](../../../framework/reflection-and-codedom/reflection.md)
