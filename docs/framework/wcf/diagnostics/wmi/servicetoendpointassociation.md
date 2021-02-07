---
description: 다음에 대해 자세히 알아보세요. ServiceToEndpointAssociation
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 1ae2ce2bcc0b3494b00fffa750f3ca46d26fe08f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715342"
---
# <a name="servicetoendpointassociation"></a>ServiceToEndpointAssociation

서비스를 엔드포인트에 매핑합니다.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a>메서드  

 ServiceToEndpointAssociation 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 ServiceToEndpointAssociation 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="ref"></a>ref  

 데이터 형식: Service  
  
 액세스 형식: 읽기 전용  
한정자: Key  
  
 엔드포인트와 연결된 서비스입니다.  
  
### <a name="ref"></a>ref  

 데이터 형식: Endpoint  
  
 액세스 형식: 읽기 전용  
한정자: Key  
  
 서비스와 연결된 엔드포인트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
