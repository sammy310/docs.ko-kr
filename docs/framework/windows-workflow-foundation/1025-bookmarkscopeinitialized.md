---
description: '자세한 정보: 1025-BookmarkScopeInitialized'
title: 1025 - BookmarkScopeInitialized
ms.date: 03/30/2017
ms.assetid: 63584434-e709-471d-9e96-97d3d99e70d6
ms.openlocfilehash: 22e686253fc5d580fba453950825072667247fad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755501"
---
# <a name="1025---bookmarkscopeinitialized"></a>1025 - BookmarkScopeInitialized

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1025|  
|키워드|WFRuntime|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 BookmarkScope가 초기화되었음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 TemporaryId: '%1'인 BookmarkScope가 Id: '%2'(으)로 초기화되었습니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|TemporaryId|xs:string|책갈피의 임시 ID입니다.|  
|InitializedId|xs:string|책갈피의 초기화된 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
