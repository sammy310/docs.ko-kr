---
title: Put 함수 (관리 되지 않는 API 참조)
description: Put 함수는 명명 된 속성에 새 값을 할당 합니다.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f1bb8aa09a269e3b8fd23f393d63a275d308a77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127398"
---
# <a name="put-function"></a>Put 함수

명명된 속성을 새 값으로 설정합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a>매개 변수

`vFunc`\
진행 이 매개 변수는 사용 되지 않습니다.

`ptr`\
진행 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대 한 포인터입니다.

`wszName`\
진행 속성의 이름입니다. 이 매개 변수를 `null`수 없습니다.

`lFlags`\
[in] 예약되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pVal`\
진행 새 속성 값이 될 유효한 `VARIANT`에 대 한 포인터입니다. `pVal`이 `null` 되거나 `VT_NULL`형식의 `VARIANT`을 가리키는 경우 속성은 `null`로 설정 됩니다.

`vtType`\
진행 `pVal`가 가리키는 `VARIANT`의 형식입니다. 자세한 내용은 [설명](#remarks) 부분을 참조 하세요.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값은 *WbemCli* 헤더 파일에 정의 되어 있거나 코드에서 상수로 정의할 수 있습니다.

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 잘못 되었습니다. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | 속성 유형을 인식할 수 없습니다. 클래스가 이미 있는 경우 클래스 인스턴스를 만들 때이 값이 반환 됩니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Instances: `pVal`가 속성에 대해 잘못 된 형식의 `VARIANT`를 가리키도록 지정 합니다. <br/> 클래스 정의의 경우: 속성이 이미 부모 클래스에 있으며 새 COM 형식이 이전 COM 형식과 다릅니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출에 성공 했습니다. |

## <a name="remarks"></a>주의

이 함수는 [IWbemClassObject::P 세계](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드에 대 한 호출을 래핑합니다.

이 함수는 항상 현재 속성 값을 새 값으로 덮어씁니다. [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 가 클래스 정의를 가리키는 경우 속성 값을 만들거나 업데이트 `Put` 합니다. [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 가 CIM 인스턴스를 가리키면 `Put`는 속성 값만 업데이트 합니다. `Put` 속성 값을 만들 수 없습니다.

`__CLASS` system 속성은 비워 둘 수 없는 경우 클래스를 만드는 동안에만 쓸 수 있습니다. 다른 모든 시스템 속성은 읽기 전용입니다.

사용자는 이름이 밑줄 ("_")로 시작 하거나 끝나는 속성을 만들 수 없습니다. 이는 시스템 클래스 및 속성에 대해 예약 되어 있습니다.

`Put` 함수에 의해 설정 된 속성이 부모 클래스에 있으면 속성 형식이 부모 클래스 형식과 일치 하지 않는 경우 속성의 기본값이 변경 됩니다. 속성이 존재 하지 않고 형식이 일치 하지 않으면 속성이 생성 됩니다.

CIM 클래스 정의에 새 속성을 만들 때만 `vtType` 매개 변수를 사용 하 고 `pVal` `null` 또는 `VT_NULL`형식의 `VARIANT`를 가리키도록 합니다. 이 경우 `vType` 매개 변수는 속성의 CIM 형식을 지정 합니다. 다른 모든 경우에는 `vtType` 0 이어야 합니다. 속성의 형식이 고정 되어 있고 변경할 수 없기 때문에 기본 개체가 인스턴스인 경우 (`Val` `null`경우에도) `vtType` 0 이어야 합니다.

## <a name="example"></a>예제

예제를 보려면 [IWbemClassObject::P 세계](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드를 참조 하세요.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** WMINet_Utils

**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참조

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
