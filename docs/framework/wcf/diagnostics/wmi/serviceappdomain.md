---
description: '자세한 정보: ServiceAppDomain'
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 1ac32b1fbd88518ffb260be9dd3ed2adb88d211c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715641"
---
# <a name="serviceappdomain"></a>ServiceAppDomain

서비스를 애플리케이션 도메인에 매핑합니다.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a>메서드  

 ServiceAppDomain 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 ServiceAppDomain 클래스에는 다음 속성이 포함되어 있습니다.  
  
### <a name="ref"></a>ref  

 데이터 형식: Service  
한정자: Key  
  
 액세스 형식: 읽기 전용  
  
 이 애플리케이션 도메인의 서비스입니다.  
  
### <a name="ref"></a>ref  

 데이터 형식: AppDomainInfo  
한정자: Key  
  
 액세스 형식: 읽기 전용  
  
 애플리케이션 도메인의 속성을 포함합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
