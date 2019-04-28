---
title: '방법: 포함 리소스에 표준 시간대 저장'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c67a97193d186275e6a788f6b18bbc17c535f367
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912706"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>방법: 포함 리소스에 표준 시간대 저장

표준 시간대 인식 응용 프로그램이 종종 특정 표준 시간대가 있어야 합니다. 그러나 때문에 개별 가용성 <xref:System.TimeZoneInfo> 로컬 시스템의 레지스트리에 저장 된 정보에 종속 된 개체, 관례적으로 사용할 수 있는 표준 시간대는 없을 수 있습니다. 사용자 지정 표준 시간대에 대 한 정보를 사용 하 여 인스턴스화된 또한는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드는 레지스트리의 다른 표준 시간대 정보를 사용 하 여 저장 되지 않습니다. 이러한 표준 시간대는 필요할 때 사용할 수 있도록를 직렬화 하 여 저장할 수 있으며 나중 역직렬화 하 여 복원할 수 있습니다.

일반적으로 직렬화 하는 작업을 <xref:System.TimeZoneInfo> 개체는 표준 시간대 인식 응용 프로그램 외에도 발생 합니다. Serialize 된 보유 하는 데 사용 되는 데이터 저장소에 따라 <xref:System.TimeZoneInfo> 또는 유틸리티를 실행 하는 과정의 일환 (예를 들어 데이터 응용 프로그램 레지스트리 키에 저장 된 경우)를 설치 하거나 설치 과정의 일환으로 표준 시간대 데이터를 직렬화 할 개체 전에 최종 응용 프로그램 (예를 들어 경우 serialize 된 데이터는.NET XML 리소스 (.resx) 파일에 저장 됨) 컴파일됩니다.

응용 프로그램을 사용 하 여 컴파일되는 리소스 파일 외에도 표준 시간대 정보에 대 한 몇 가지 다른 데이터 저장소를 사용할 수 있습니다. 이러한 요구 사항은 다음과 같습니다.

* 레지스트리입니다. HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time 영역의 하위 키를 사용 하는 것이 아니라 사용자 지정 표준 시간대 데이터를 저장 하는 응용 프로그램 자체 응용 프로그램 키의 하위 키를 사용 해야 함을 note 합니다.

* 구성 파일입니다.

* 다른 시스템 파일입니다.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>.Resx 파일에 직렬화 하 여 표준 시간대 저장

1. 새 표준 시간대를 만들거나 기존 표준 시간대를 검색 합니다.

   기존 표준 시간대를 검색 하려면 참조 [방법: 미리 정의 된 UTC 및 현지 표준 시간대 개체에 액세스할](../../../docs/standard/datetime/access-utc-and-local.md) 고 [방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)합니다.

   새 표준 시간대를 만들려면 오버 로드 중 하나를 호출 합니다 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드. 자세한 내용은 [방법: 표준 시간대 조정 규칙 없이 만들](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 고 [방법: 표준 시간대 조정 규칙을 사용 하 여 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다.

2. 호출 된 <xref:System.TimeZoneInfo.ToSerializedString%2A> 시간대의 데이터가 들어 있는 문자열을 만드는 방법.

3. 인스턴스화하는 <xref:System.IO.StreamWriter> 이름 및 필요에 따라.resx 파일의 경로 제공 하 여 개체를 <xref:System.IO.StreamWriter> 클래스 생성자입니다.

4. 인스턴스화하는 <xref:System.Resources.ResXResourceWriter> 전달 하 여 개체를 <xref:System.IO.StreamWriter> 개체를 <xref:System.Resources.ResXResourceWriter> 클래스 생성자입니다.

5. 전달 된 표준 시간대의 문자열을 직렬화 합니다 <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> 메서드.

6. <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 메서드를 호출합니다.

7. <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> 메서드를 호출합니다.

8. 닫기 합니다 <xref:System.IO.StreamWriter> 개체를 호출 하 여 해당 <xref:System.IO.StreamWriter.Close%2A> 메서드.

9. 응용 프로그램의 Visual Studio 프로젝트에 생성 된.resx 파일을 추가 합니다.

10. 사용 하 여는 **속성** Visual Studio에서 창 했는지.resx 파일의 **빌드 작업** 속성이로 설정 되어 **포함 리소스**합니다.

## <a name="example"></a>예제

다음 예제에서는 serialize 된 <xref:System.TimeZoneInfo> 중부 표준시를 나타내는 개체 및 <xref:System.TimeZoneInfo> SerializedTimeZones.resx 라는.NET XML 리소스 파일에 파머 기지, 남극 대륙 시간을 나타내는 개체입니다. 중부 표준시는 일반적으로 레지스트리에; 정의 파머 기지, 남극 대륙에 사용자 지정 시간 영역입니다.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

이 예제에서는 serialize <xref:System.TimeZoneInfo> 되도록 사용할 수 있는 리소스 파일에 컴파일 타임에 개체입니다.

때문에 <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> .NET XML 리소스 파일에 전체 헤더 정보를 추가 하는 메서드, 기존 파일에 리소스를 추가 하려면 사용할 수 없습니다. 예제 SerializedTimeZones.resx 파일을 확인 하 여이 처리 하 고 존재 하는 경우 모든 해당 리소스가 아닌 다른 저장 두 직렬화 된 표준 시간대를 제네릭 <xref:System.Collections.Generic.Dictionary%602> 개체입니다. 기존 파일은 삭제 되 고 기존 리소스를 새 SerializedTimeZones.resx 파일에 추가 됩니다. Serialize 된 표준 시간대 데이터도이 파일에 추가 됩니다.

키 (또는 **이름을**) 리소스의 필드에는 공백이 없어야 합니다. <xref:System.String.Replace%28System.String%2CSystem.String%29> 메서드를 호출 하는 리소스 파일에 할당 되기 전에 표준 시간대 식별자에 포함 된 모든 공백을 제거 합니다.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Windows.Forms.dll System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스를 가져와야 합니다.

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>참고자료

- [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
- [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
- [방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
