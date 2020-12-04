---
title: 불필요한 코드 규칙
description: 코드 분석 불필요 한 코드 규칙에 대 한 자세한 정보
ms.date: 09/30/2020
ms.topic: reference
author: gewarren
ms.author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 16c4ba0e4bee2388736bf9813a3e8290d8d4da32
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "96593859"
---
# <a name="unnecessary-code-rules"></a>불필요한 코드 규칙

불필요 한 코드 규칙은 코드 베이스에서 불필요 하 고 리팩터링 또는 제거할 수 있는 여러 부분을 식별 합니다. 불필요 한 코드가 있으면 다음 문제 중 하나를 나타냅니다.

- 가독성: 가독성을 불필요 하 게 저하 하는 코드입니다. 예를 들어 [IDE0001](ide0001.md) 는 불필요 한 형식 이름 한정을 플래그 합니다.
- 유지 관리: 리팩터링 후 더 이상 사용 되지 않고 불필요 하 게 유지 관리 되는 코드입니다. 예를 들어, [IDE0051](ide0051.md) 는 사용 되지 않는 전용 필드, 속성, 이벤트 및 메서드에 플래그를 사용 합니다.
- 성능: 부작용이 없고 불필요 한 성능 오버 헤드를 초래 하는 불필요 한 계산입니다. 예를 들어, [IDE0059](ide0059.md) 는 값을 계산 하는 식에 파생 작업이 없는 경우 사용 하지 않는 값 할당 플래그를 지정 합니다.
- 기능: 코드의 기능 문제로 인해 필요한 코드가 중복 렌더링 됩니다. 예를 들어, [IDE0060](ide0060.md) 는 메서드가 입력 매개 변수를 실수로 무시 하는 사용 되지 않는 매개 변수를 플래그 합니다.

이 단원의 규칙은 다음과 같은 불필요 한 코드 규칙을 고려 합니다.

- [이름 단순화 (IDE0001)](ide0001.md)
- [멤버 액세스 간소화 (IDE0002)](ide0002.md)
- [불필요 한 캐스트 제거 (IDE0004)](ide0004.md)
- [불필요 한 가져오기 제거 (IDE0005)](ide0005.md)
- [접근할 수 없는 코드 제거 (IDE0035)](ide0035.md)
- [사용 하지 않는 전용 구성원 제거 (IDE0051)](ide0051.md)
- [읽지 않은 전용 구성원 제거 (IDE0052)](ide0052.md)
- [사용 하지 않는 식 값 제거 (IDE0058)](ide0058.md)
- [불필요 한 값 할당 제거 (IDE0059)](ide0059.md)
- [사용 하지 않는 매개 변수 제거 (IDE0060)](ide0060.md)
- [불필요 한 비 표시 제거 (IDE0079)](ide0079.md)
- [불필요 한 비 표시 제거 연산자 (IDE0080)](ide0080.md) -c #에만 해당 합니다.
- [' ByVal ' (IDE0081)](ide0081.md) -Visual Basic만 제거 합니다.
- [불필요 한 같음 연산자 제거 (IDE0100)](ide0100.md)
- [불필요 한 삭제 (IDE0110)를 제거](ide0110.md) 합니다.-c #만 해당 합니다.

이러한 규칙 중 일부에는 규칙 동작을 구성 하는 옵션이 있습니다.

- [csharp_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#csharp_style_unused_value_expression_statement_preference)
- [visual_basic_style_unused_value_expression_statement_preference (IDE0058)](ide0058.md#visual_basic_style_unused_value_expression_statement_preference)
- [csharp_style_unused_value_assignment_preference (IDE0059)](ide0059.md#csharp_style_unused_value_assignment_preference)
- [visual_basic_style_unused_value_assignment_preference (IDE0059)](ide0059.md#visual_basic_style_unused_value_assignment_preference)
- [dotnet_code_quality_unused_parameters (IDE0060)](ide0060.md#dotnet_code_quality_unused_parameters)
- [dotnet_remove_unnecessary_suppression_exclusions (IDE0079)](ide0079.md#dotnet_remove_unnecessary_suppression_exclusions)

## <a name="see-also"></a>참고 항목

- [코드 스타일 언어 규칙](language-rules.md)
- [코드 스타일 규칙 참조](index.md)
