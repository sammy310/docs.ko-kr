---
description: '자세한 정보: 1004-WorkflowInstanceAborted'
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: 4aaa0899da9b0b8510684a13537a8cb8f9117ee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755621"
---
# <a name="1004---workflowinstanceaborted"></a>1004 - WorkflowInstanceAborted

## <a name="properties"></a>속성

|||
|-|-|
|ID|1004|
|키워드|WFRuntime|
|Level|정보|
|채널|Microsoft-Windows-애플리케이션 서버-애플리케이션/디버그|

## <a name="description"></a>설명

워크플로 인스턴스가 예외와 함께 중단 되었음을 나타냅니다.

## <a name="message"></a>메시지

WorkflowInstance Id: '%1'이(가) 예외와 함께 중단되었습니다.

## <a name="details"></a>세부 정보

|데이터 항목 이름|데이터 항목 형식|설명|
|--------------------|--------------------|-----------------|
|WorkflowInstanceId|`xs:string`|워크플로의 인스턴스 ID|
|예외|`xs:string`|예외에 대한 예외 정보|
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
