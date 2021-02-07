---
description: '자세한 정보: 바인딩'
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 36887a9296bfafd0790105e7f4d513efc3009bf8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757789"
---
# <a name="binding"></a>바인딩

wmi 바인딩  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a>메서드  

 Binding 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 바인딩 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="bindingelements"></a>BindingElements  

 데이터 형식: BindingElement array  
  
 액세스 형식: 읽기 전용  
  
 바인딩이 구현한 바인딩 요소의 컬렉션입니다.  
  
### <a name="closetimeout"></a>CloseTimeout  

 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 닫기 작업을 완료하기 위해 제공된 시간 간격입니다.  
  
### <a name="name"></a>Name  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 바인딩 이름입니다.  
  
### <a name="namespace"></a>네임스페이스  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 바인딩의 XML 네임스페이스입니다.  
  
### <a name="opentimeout"></a>OpenTimeout  

 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 열기 작업을 완료하기 위해 제공된 시간 간격입니다.  
  
### <a name="receivetimeout"></a>ReceiveTimeout  

 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 받기 작업을 완료하기 위해 제공된 시간 간격입니다.  
  
### <a name="scheme"></a>구성표  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 바인딩이 빌드한 채널 및 수신기 팩터리에서 사용하는 URI 전송 체계입니다.  
  
### <a name="sendtimeout"></a>SendTimeout  

 데이터 형식: datetime  
  
 액세스 형식: 읽기 전용  
  
 보내기 작업을 완료하기 위해 제공된 시간 간격입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Channels.Binding>
