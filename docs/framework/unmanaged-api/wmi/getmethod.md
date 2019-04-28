---
title: GetMethod 함수 (관리 되지 않는 API 참조)
description: GetMethod 함수 메서드에 대 한 정보를 검색합니다.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb8919e8760616676ea5ff99069e2d2ceb5f7451
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608920"
---
# <a name="getmethod-function"></a>GetMethod 함수

지정된 메서드에 대한 정보를 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a>매개 변수

`vFunc`\
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`\
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`wszName`\
[in] 메서드 이름입니다. 이 매개 변수 수 없습니다 `null` 유효한 가리켜야 `LPCWSTR`합니다.

`lFlags`\
[in] 예약되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`ppInSignature`\
[out] 주소에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 in 매개 변수를 설명 하는 인스턴스입니다. 로 설정 된 경우이 매개 변수가 무시 됩니다 `null`합니다.

`ppOutSignature`\
[out] 주소에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 out 매개 변수를 설명 하는 인스턴스입니다. 로 설정 된 경우이 매개 변수가 무시 됩니다 `null`합니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 속성을 찾을 수 없습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) 메서드.

Windows 관리를 설정할 수는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 에 대 한 포인터 `null` 메서드 매개 변수가 없는 경우에 합니다.

`ppInSignature` 하 고 `ppOutSignature` in 및 out 매개 변수를 각각의 속성으로 설명를 `IWbemClassObject` 시스템 클래스의 인스턴스 [_Parameters](/windows/desktop/WmiSdk/--parameters)합니다. 속성 `ppInSignature` 라고 `Param` *n*여기서 *n* 메서드 시그니처에서 매개 변수의 위치입니다 (같은 `Param1`, `Param2`등.). 속성 `ppOutSignature` 이 라고도 `Param` *n*, 및 반환 값은 명명 된 `ReturnValue`합니다. 자세한 내용 및 예제를 참조 하세요 [IWbemClassObject::GetMethod 메서드](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** WMINet_Utils.idl

**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)