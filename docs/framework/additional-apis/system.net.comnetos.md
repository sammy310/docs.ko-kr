---
description: '자세한 정보: ComNetOS 클래스'
title: ComNetOS 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7376fe4a5e02818907cb71573451fffb3a3667cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802530"
---
# <a name="comnetos-class"></a>ComNetOS 클래스

현재 운영 체제에 대 한 정보 (예: 버전 및 설치 유형 (클라이언트 또는 서버))를 제공 합니다. 이 클래스는 상속될 수 없습니다.
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="iswin7orlater-field"></a>IsWin7orLater 필드

운영 체제 버전이 Windows 7 이상 인지 여부를 지정 합니다.

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
