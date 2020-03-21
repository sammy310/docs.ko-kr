---
title: BlessIWbemServicesObject 함수(관리되지 않는 API 참조)
description: BlessIWbemServicesObject 함수는 사용자 자격 증명이 IWbemServices 개체에 대한 액세스를 허용하는지 여부를 나타냅니다.
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175033"
---
# <a name="blessiwbemservicesobject-function"></a>BlessIWbemServicesObject 함수
사용자 자격 증명이 지정된 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체에 대한 액세스를 허용하는지 여부를 나타냅니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a>매개 변수

`pIWbemServices`\
【인】 WMI 서비스 개체에 대한 포인터입니다.

`strUser`\
【인】 사용자 이름입니다.

`strPassword`\
【인】 와 연결된 `strUser`암호입니다.

`strAuthority`\
【인】 사용자의 도메인 이름입니다. 자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.

`impLevel`\
【인】 가장 수준입니다.

`authnLevel`\
【인】 권한 부여 수준입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WinError.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | 하나 이상의 인수가 유효하지 않습니다. |
| `E_POINTER` | 0x80004003 | `pIWbemServices`은 `null`입니다. |
| `E_FAIL` | 0x80000008 | 알 수 없는 오류가 발생했습니다. |
| `E_OUTOFMEMORY` | 0x80000002 | 작업을 수행하기 위해 메모리가 부족합니다. |
| `S_OK` | 0 | 함수 호출이 성공했습니다. |

## <a name="requirements"></a>요구 사항

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

 **헤더:** WMINet_Utils.idl

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
