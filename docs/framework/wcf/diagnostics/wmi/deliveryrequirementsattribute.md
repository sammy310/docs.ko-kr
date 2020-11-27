---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274051"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute

DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>구문  
  
```csharp
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>메서드  

 DeliveryRequirementsAttribute 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 DeliveryRequirementsAttribute 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 서비스 바인딩이 계약을 지원할지 여부를 지정합니다.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  

 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 바인딩이 순서가 지정된 메시지를 지원할지 여부를 지정합니다.  
  
### <a name="targetcontract"></a>TargetContract  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 적용할 계약입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
