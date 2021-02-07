---
description: '자세한 정보: 111-CustomTrackingRecordError'
title: 111 - CustomTrackingRecordError
ms.date: 03/30/2017
ms.assetid: d469fb12-e094-4d6c-9b4d-abd7ce0d17da
ms.openlocfilehash: 7e93d0c1e00e3120f647dda5690e84f758c3ee14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667475"
---
# <a name="111---customtrackingrecorderror"></a>111 - CustomTrackingRecordError

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|Id|111|  
|키워드|UserEvents, EndToEndMonitoring, 문제 해결, HealthMonitoring, WFTracking|  
|Level|Error|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 워크플로 인스턴스 내의 활동에서 오류 수준의 CustomTrackingRecord를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.  
  
## <a name="message"></a>메시지  

 TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|워크플로의 인스턴스 ID|  
|RecordNumber|xs:long|내보낸 레코드의 시퀀스 번호|  
|EventTime|xs:dateTime|이벤트를 내보낸 시간(UTC)|  
|Name|xs:string|CustomTrackingRecord의 이름|  
|ActivityName|xs:string|CustomTrackingRecord를 내보낸 활동의 이름|  
|ActivityId|xs:string|CustomTrackingRecord를 내보낸 활동의 ID|  
|ActivityInstanceId|xs:string|CustomTrackingRecord를 내보낸 활동의 인스턴스 ID|  
|ActivityTypeName|xs:string|CustomTrackingRecord를 내보낸 활동의 이름|  
|데이터|xs:string|이 이벤트를 사용하여 추적된 데이터입니다.  값은 datavalue 형식의 xml 요소에 저장 됩니다 \<items> \< item  name = "dataName" type="System.String"> \</item> \</items> .  추적 된 데이터가 없으면 문자열에가 포함 \<items/> 됩니다. ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다. 이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 데이터 값을 ...로 대체 하 여 이벤트를 자릅니다. \<items> \</items>  다음 형식은 ToString ()에서 반환 된 값으로 저장 됩니다. string, char, bool, int, short, long, uint, ushort, ulong, system.string, float, double, system.string, system.string, System.web.  모든 다른 형식은 System.Runtime.Serialization.NetDataContractSerializer를 사용하여 serialize됩니다.|  
|주석|xs:string|이 이벤트에 추가된 주석입니다.  값은 xml 요소에 a 형식으로 저장 됩니다 \<items> \< item  name = "annotationName" type="System.String"> \</item> \</items> .  주석을 지정 하지 않으면 문자열에가 포함 \<items/> 됩니다. ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다. 이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값을 ...로 대체 하 여 이벤트를 자릅니다. \<items> \</items>|  
|ProfileName|xs:string|이 이벤트를 내보낸 이름 또는 추적 프로필|  
|HostReference|xs:string|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.  해당 형식은 ' 웹 사이트 이름 응용 프로그램 가상 경로&#124;서비스 가상 경로&#124;ServiceName ' 예: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '로 정의 됩니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
