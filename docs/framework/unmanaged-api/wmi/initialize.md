---
title: Initialize 함수 (관리 되지 않는 API 참조)
description: Initialize 함수는 WMI 초기화를 수행 합니다.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127387"
---
# <a name="initialize-function"></a>Initialize 함수

WMI 초기화를 수행합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a>매개 변수

`bAllowIManagementObjectQI`

[in] WMI 개체에 대 한 QueryInterface 호출이 허용 됨을 나타내는 `true`입니다. 그렇지 않으면 `false` 합니다.

## <a name="return-value"></a>반환 값

함수는 항상 `S_OK` (0)를 반환 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** WMINet_Utils

**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참조

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
