---
title: Put 함수 (관리 되지 않는 API 참조)
description: Put 함수는 명명 된 속성에 새 값을 할당합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02c8ab3aa7fcc603b76fb4b1d09e7e73d04494be
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369198"
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
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`\
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`wszName`\
[in] 속성의 이름입니다. 이 매개 변수 수 없습니다 `null`합니다.

`lFlags`\
[in] 예약되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pVal`\
[in] 유효한 포인터 `VARIANT` 는 새 속성 값이 됩니다. 경우 `pVal` 됩니다 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`, 속성이 설정 되어 `null`입니다.

`vtType`\
[in] 유형의 `VARIANT` 가리키는 `pVal`합니다. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 올바르지 않습니다. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | 속성 형식이 인식 되지 않습니다. 클래스가 이미 존재 하는 경우 클래스 인스턴스를 만들 때이 값이 반환 됩니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | 에 대 한 인스턴스: 함을 `pVal` 가리키는 `VARIANT` 속성에 대 한 잘못 된 형식입니다. <br/> 클래스 정의: 속성이 부모 클래스에 이미 있습니다. 및 새 COM 형식은 이전 COM 유형과 다릅니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다. |

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드.

이 함수는 항상 새 리소스를 사용 하 여 현재 속성 값을 덮어씁니다. 경우는 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 클래스 정의 가리키는 `Put` 만들거나 속성 값을 업데이트 합니다. 때 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 `Put` 만; 속성 값을 업데이트 합니다. `Put` 속성 값을 만들 수 없습니다.

`__CLASS` 시스템 속성은 쓰기 가능한 클래스를 만드는 동안 경우에 해당 하지 비어 있을 수 있습니다. 다른 모든 시스템 속성은 읽기 전용입니다.

사용자 이름이 밑줄 ("_")으로 시작 하거나 끝날 하는 속성을 만들 수 없습니다. 이 시스템 클래스 및 속성에 대해 예약 됩니다.

속성으로 설정 하는 경우는 `Put` 함수가 있는 부모 클래스, 부모 클래스 유형 속성 형식에 맞지 않으면 속성의 기본 값이 변경 됩니다. 속성이 존재 하지 않습니다 하 고 형식이 일치 하지 않습니다, 경우 속성이 만들어집니다.

사용 하 여는 `vtType` CIM 클래스 정의에 새 속성을 만드는 경우에 매개 변수 및 `pVal` 됩니다 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`합니다. 이 경우에 `vType` 매개 변수 속성의 CIM 형식을 지정 합니다. 다른 모든 경우에서 `vtType` 0 이어야 합니다. `vtType` 기본 개체 인스턴스이면 0 수도 있어야 합니다 (경우에 `Val` 는 `null`) 속성의 형식 고정 되어 변경할 수 없으므로 합니다.

## <a name="example"></a>예제

예를 들어 참조 된 [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) 메서드.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

**헤더:** WMINet_Utils.idl

**.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)