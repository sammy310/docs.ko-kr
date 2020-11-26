---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239836"
---
# <a name="1006---workflowapplicationunhandledexception"></a>1006 - WorkflowApplicationUnhandledException

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1006|  
|키워드|WFRuntime|  
|Level|오류|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>Description  

 워크플로 애플리케이션에서 처리되지 않은 예외가 발생했음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 WorkflowInstance Id: ' %1 '에서 처리 되지 않은 예외가 발생 했습니다.  작업 ' %2 ', DisplayName: ' %3 '에서 예외가 발생 했습니다.  다음 작업이 수행 됩니다. %4.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|Description|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|워크플로의 인스턴스 ID|  
|예외|`xs:string`|예외에 대한 예외 정보|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
