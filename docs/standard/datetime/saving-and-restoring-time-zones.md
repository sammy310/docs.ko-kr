---
title: 표준 시간대 저장 및 복원
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d783f9e0d098e472dcf67aea394804d6eef2662
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026525"
---
# <a name="saving-and-restoring-time-zones"></a>표준 시간대 저장 및 복원

<xref:System.TimeZoneInfo> 미리 정의 된 표준 시간대 데이터를 검색할 레지스트리 의존 하는 클래스입니다. 그러나 레지스트리는 동적 구조입니다. 또한 레지스트리에 포함 된 표준 시간대 정보는 운영 체제에서 현재 연도 대 한 시간 조정 및 변환을 처리 하는 데 주로 사용 됩니다. 여기에 정확 하 게 표준 시간대 데이터에 의존 하는 응용 프로그램에 대 한 두 가지 주요 의미가 있습니다.

* 레지스트리에서 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다 하거나 해당 있습니다 바뀌거나 레지스트리에서 제거 합니다.

* 레지스트리에 정의 된 표준 시간대에는 기록 표준 시간대 변환에 필요한 특정 조정 규칙에 대 한 정보가 없을 수 있습니다.

<xref:System.TimeZoneInfo> (저장) serialization 및 deserialization (복원)의 표준 시간대 데이터에 대 한 지원을 통해 이러한 한계를 해결 하는 클래스입니다.

## <a name="time-zone-serialization-and-deserialization"></a>표준 시간대 serialization 및 deserialization

저장 및 직렬화 및 표준 시간대 데이터를 역직렬화 하 여 표준 시간대 복원 두 메서드 호출을 수행 해야 합니다.

* Serialize 할 수 있습니다는 <xref:System.TimeZoneInfo> 해당 개체를 호출 하 여 개체 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드. 메서드 매개 변수를 사용 하 고 표준 시간대 정보가 포함 된 문자열을 반환 합니다.

* Deserialize 할 수는 <xref:System.TimeZoneInfo> 해당 문자열을 전달 하 여 serialize 된 문자열에서 개체를 `static` (`Shared` Visual basic에서) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> 메서드.

## <a name="serialization-and-deserialization-scenarios"></a>Serialization 및 deserialization 시나리오

저장 (또는 직렬화) 하는 기능을 <xref:System.TimeZoneInfo> 나중에 사용할 개체를 문자열로 및 복원 (또는 역직렬화)를 증가 유틸리티와의 유연성을 <xref:System.TimeZoneInfo> 클래스입니다. 이 섹션에서는 몇 가지는 serialization 및 deserialization에는 가장 유용한 상황 검사 합니다.

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a>직렬화 및 역직렬화 응용 프로그램에서 표준 시간대 데이터

필요한 경우 serialize 된 표준 시간대 문자열에서 복원할 수 있습니다. 레지스트리에서 검색할 표준 시간대 날짜 및 시간을 특정 날짜 범위 내에서 정확 하 게 변환할 수 없는 경우 응용 프로그램은이 수행할 수 있습니다. 예를 들어, Windows XP 레지스트리에서 표준 시간대 데이터는 일반적으로 Windows Vista 레지스트리에 정의 된 표준 시간대 조정 규칙에 대 한 두 가지 정보를 제공 하는 동안에 하나의 조정 규칙을 지원 합니다. 이 과거 시간 변환 정확 하지 않을 것을 의미 합니다. 표준 시간대 데이터의 serialization 및 deserialization에는이 제한을 처리할 수 있습니다.

다음 예제에서는 사용자 지정에서에서 <xref:System.TimeZoneInfo> 미국을 나타내도록 조정 규칙 없이 클래스 정의 동부 표준 시간대에서에서 1917 년 미국의 일광 절약 시간제를 도입 하기 전에 합니다. 사용자 지정 표준 시간대는 전역 범위가 있는 변수에 serialize 됩니다. 표준 시간대 변환 메서드 `ConvertUtcTime`, UTC (Coordinated Universal Time) 시간 변환에 전달 됩니다. 날짜 및 시간 또는 이전 버전에서 1917 발생 하는 경우 사용자 지정 동부 표준시 표준 시간대 serialize 된 문자열에서 복원 되 고 레지스트리에서 검색할 표준 시간대를 바꿉니다.

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a>표준 시간대 예외 처리

레지스트리는 동적 구조 이므로 내용이 실수나 고의로 수정 적용 됩니다. 즉, 시간대 레지스트리에 정의 되어 있어야 하 고 성공적으로 실행 하도록 응용 프로그램에 필요한 매개 변수가 없을 수도 있습니다. 표준 시간대 serialization 및 deserialization에 대 한 지원은 결과 처리 하지만 선택의 여지가 거의 해야 <xref:System.TimeZoneNotFoundException> 응용 프로그램을 종료 하 여 합니다. 그러나 표준 시간대 직렬화 및 역직렬화를 사용 하 여 처리할 수 있습니다 예기치 않은 <xref:System.TimeZoneNotFoundException> 복원 하 여 필요한 표준 시간대는 직렬화 된 문자열 및 응용 프로그램에서 계속 실행 됩니다.

다음 예제에서는 만들고 사용자 지정 중앙 표준 시간대를 serialize 합니다. 그런 다음 레지스트리에서 중앙 표준 시간대를 검색 하려고 합니다. 검색 작업 중 하나를 throw 하는 경우는 <xref:System.TimeZoneNotFoundException> 또는 <xref:System.InvalidTimeZoneException>, 예외 처리기는 표준 시간대를 역직렬화 합니다.

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a>직렬화 된 문자열을 저장 하 고 필요에 따라 복원

앞의 예제에서는 문자열 변수에 표준 시간대 정보를 저장 있고 필요에 따라 복원 됩니다. 그러나 응용 프로그램 또는 레지스트리에서 영역 정보 자체에 저장할 수는 외부 파일에 리소스와 같은 일부 저장소 매체에 serialize 된 시간을 포함 하는 문자열 포함 합니다. (참고 하 여 사용자 지정 표준 시간대에 대 한 정보 시스템의 표준 시간대 레지스트리 키 외에도 저장 됩니다.)

응용 프로그램 자체에서 표준 시간대 생성 루틴을 구분도이 방식으로 직렬화 된 표준 시간대 문자열을 저장 합니다. 예를 들어, 표준 시간대 생성 루틴을 실행 하 고 응용 프로그램에서 사용할 수 있는 기록 표준 시간대 정보를 포함 하는 데이터 파일을 만들 수 있습니다. 데이터 파일 수를 응용 프로그램을 함께 설치할 수 열 수 있습니다 및 응용 프로그램을 사용 해야 하는 경우 하나 이상의 해당 표준 시간대를 deserialize 할 수 있습니다.

Serialize 된 표준 시간대 데이터를 저장 하는 포함된 리소스를 사용 하는 예제를 참조 하세요. [방법: 포함된 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 고 [방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)합니다.

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
