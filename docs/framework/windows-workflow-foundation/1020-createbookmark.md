---
description: '자세한 정보: 1020-CreateBookmark'
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 39796eaf68d9cb52e9faa2605fc21955a2c167ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792845"
---
# <a name="1020---createbookmark"></a>1020 - CreateBookmark

## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1020|  
|키워드|WFRuntime|  
|Level|자세히|  
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|  
  
## <a name="description"></a>설명  

 작업에 대한 책갈피가 만들어졌음을 나타냅니다.  
  
## <a name="message"></a>메시지  

 작업 ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '에 대 한 책갈피를 만들었습니다.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|활동|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|BookmarkName|xs:string|책갈피 이름입니다.|  
|BookmarkScope|xs:string|책갈피의 범위입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
