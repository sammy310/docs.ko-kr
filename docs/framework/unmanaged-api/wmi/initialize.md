---
title: Initialize 함수 (관리 되지 않는 API 참조)
description: Initialize 함수 WMI 초기화를 수행합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611083"
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

[in] `true` WMI 개체에서 QueryInterface 호출할 수 있도록; 나타내려면 `false` 그렇지 않은 경우.

## <a name="return-value"></a>반환 값

항상 반환 `S_OK` (0).

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** WMINet_Utils.def

**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
