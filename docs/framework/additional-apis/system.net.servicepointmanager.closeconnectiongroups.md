---
description: '자세한 정보: ServicePointManager 메서드'
title: ServicePointManager 메서드 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 8cd1a1f0f4dbdaeaee117e6a7ae4219680363a6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699560"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a>ServicePointManager 메서드

모든 서비스 요소를 반복 하 고 지정 된 이름이 있는 연결 그룹을 닫습니다.

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> 이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.

## <a name="parameters"></a>매개 변수

`connectionGroupName` <xref:System.String>

닫을 연결 그룹의 이름입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
