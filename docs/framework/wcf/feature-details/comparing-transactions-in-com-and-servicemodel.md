---
title: COM+ 및 ServiceModel의 트랜잭션 비교
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 30ecbd374e909141dbc944740f90c1b41ac44ed2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264910"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>COM+ 및 ServiceModel의 트랜잭션 비교

이 항목에서는 네임 스페이스에서 제공 하는 WCF (Windows Communication Foundation) 특성을 사용 하 여 트랜잭션 COM + 서비스의 동작을 시뮬레이션 하는 방법에 대해 설명 <xref:System.ServiceModel> 합니다.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>ServiceModel 특성을 사용하여 COM+ 에뮬레이트  

 다음 표에서는 <xref:System.EnterpriseServices.TransactionOption> 트랜잭션을 만드는 데 사용 되는 열거 `EnterpriseServices` 와 이러한 열거형이 네임 스페이스에서 제공 하는 WCF 특성과 상호 관련 되는 방식을 비교 합니다 <xref:System.ServiceModel> .  
  
|COM+ 특성|WCF 특성|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute>이 <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>로 설정됩니다.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>이(가) `true`인 경우<br /><br /> 바인딩 요소의 `TransactionFlow` 특성이 `false`인 경우|  
|필수|<xref:System.ServiceModel.TransactionFlowAttribute>이 <xref:System.ServiceModel.TransactionFlowOption.Allowed>로 설정됩니다.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>이(가) `true`인 경우<br /><br /> 바인딩 요소의 `TransactionFlow` 특성이 `true`인 경우|  
|지원됨|직접 대응하는 특성이 없습니다. 일반적으로 `Required`에 지정된 동작을 대신 사용해야 합니다.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>은 `false`입니다.<br /><br /> 바인딩 요소의 `TransactionFlow` 특성이 `false`인 경우|  
|사용 안 함|직접 대응하는 특성이 없습니다. 일반적으로 `NotSupported`에 지정된 동작을 대신 사용해야 합니다.|
