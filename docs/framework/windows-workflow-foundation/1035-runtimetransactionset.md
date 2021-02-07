---
description: '자세한 정보: 1035-RuntimeTransactionSet'
title: 1035 - RuntimeTransactionSet
ms.date: 03/30/2017
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
ms.openlocfilehash: 513ba49962a8f02ab47b8e5b762949cd09154a3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667904"
---
# <a name="1035---runtimetransactionset"></a>1035 - RuntimeTransactionSet

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1035|  
|키워드|WFRuntime|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '이 (가) 런타임 트랜잭션을 설정 했습니다.  작업 ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 ' (으)로의 실행이 격리 되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|활동|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|IsolatedActivity|xs:string|트랜잭션이 격리된 작업의 형식 이름입니다.|  
|IsolatedActivityDisplayName|xs:string|트랜잭션이 격리된 작업의 표시 이름입니다.|  
|IsolatedActivityInstanceId|xs:string|트랜잭션이 격리된 작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
