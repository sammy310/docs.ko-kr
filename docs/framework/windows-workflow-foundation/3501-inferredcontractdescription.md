---
description: '자세한 정보: 3501-InferredContractDescription'
title: 3501 - InferredContractDescription
ms.date: 03/30/2017
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
ms.openlocfilehash: 2eab180780a1475bff421441b7cef23f58f627c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778089"
---
# <a name="3501---inferredcontractdescription"></a>3501 - InferredContractDescription

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3501|  
|키워드|WFServices|  
|Level|정보|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/분석|  
  
## <a name="description"></a>설명  

 ContractDescription이 WorkflowService에서 유추되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 Name='%1'이고 Namespace='%2'인 ContractDescription이 WorkflowService에서 유추되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Name|xs:string|ContractDescription의 이름입니다.|  
|네임스페이스|xs:string|ContractDescription의 네임스페이스입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
