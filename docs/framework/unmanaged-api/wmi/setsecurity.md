---
title: SetSecurity 함수(관리되지 않는 API 참조)
description: SetSecurity 함수는 현재 스레드의 가장 토큰을 검색합니다.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176736"
---
# <a name="setsecurity-function"></a>SetSecurity 함수

현재 스레드와 연결된 가장 토큰을 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a>매개 변수

`pNeedToReset`\
【아웃】 함수가 반환되면 [ResetSecurity](resetsecurity.md) `boolean` 함수를 호출하여 토큰을 재설정해야 하는지 여부를 나타내는 포인터가 포함되어 있습니다.

`token`\
【아웃】 함수가 반환되면 현재 스레드와 연결된 가장 토큰의 핸들에 대한 포인터가 포함됩니다. 해당 값은 `null` 현재 스레드와 연결된 토큰이 없는 경우일 수 있습니다.

## <a name="return-value"></a>반환 값

함수가 성공하면 반환 값은 `S_OK` (0)입니다.

함수가 실패하면 반환 값은 0이 아닌 오류 코드입니다. 확장 오류 정보를 얻으려면 [GetErrorInfo](geterrorinfo.md) 함수를 호출합니다.

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

 **헤더:** WMINet_Utils.idl

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
