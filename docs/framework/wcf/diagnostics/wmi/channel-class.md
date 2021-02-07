---
description: '자세히 알아보기: Channel 클래스'
title: Channel 클래스
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: dcc92f78f09e9a73a24134c6c0685949f46f38dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757724"
---
# <a name="channel-class"></a>Channel 클래스

채널  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>메서드  

 Channel 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 Channel 클래스에는 다음 속성이 있습니다.  
  
### <a name="localaddress"></a>LocalAddress  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 채널에 대한 로컬 엔드포인트입니다.  
  
### <a name="ref"></a>ref  

 데이터 형식: Endpoint  
  
 액세스 형식: 읽기 전용  
  
 채널이 연결되는 엔드포인트에 대한 참조입니다.  
  
### <a name="remoteaddress"></a>RemoteAddress  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 채널과 연결된 원격 주소입니다.  
  
### <a name="sessionid"></a>SessionId  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 현재 세션 ID(있는 경우)입니다.  
  
### <a name="type"></a>Type  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 채널 형식입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Channels.ChannelBase>
