---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 05278067e3f86612ee4aafbe7d5eb66dc934cb85
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242112"
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3502|  
|키워드|WFServices|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>Description  

 OperationDescription이 WorkflowService에서 유추되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 계약 '%2'에서 Name='%1'인 OperationDescription이 WorkflowService에서 유추되었습니다. IsOneWay=%3.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|작업의 이름입니다.|  
|ContractName|xs:string|계약 이름입니다.|  
|IsOneWay|xs:string|계약이 단방향인지 여부를 나타내는 True 또는 False입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
