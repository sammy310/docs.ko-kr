---
title: 시작 열거 함수(관리되지 않는 API 참조)
description: BeginEnumeration 함수는 열거형의 시작 부분으로 열거기를 재설정합니다.
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176879"
---
# <a name="beginenumeration-function"></a>BeginEnumeration 함수
열거체를 열거시작부분으로 재설정합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`\
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`\
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`lEnumFlags`\
【인】 설명 [섹션에](#remarks) 설명된 플래그 또는 값의 비트 조합으로 열거형에 포함된 속성을 제어합니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 의 `lEnumFlags` 플래그 조합이 잘못되었거나 잘못된 인수가 지정되었습니다. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 에 대한 `BeginEnumeration` 두 번째 호출은 에 [`EndEnumeration`](endenumeration.md)대한 중간 호출 없이 이루어졌습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거를 시작하기에 사용할 수 있는 메모리가 부족합니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드에 대한 호출을 래핑합니다.

`lEnumFlags` 인수로 전달할 수 있는 플래그는 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.  각 그룹의 한 플래그를 다른 그룹의 모든 플래그와 결합할 수 있습니다. 그러나 동일한 그룹의 플래그는 상호 배타적입니다.

**그룹 1**

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 키만 을 구성하는 속성을 포함합니다. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 개체 참조인 속성만 포함합니다. |

**그룹 2**

지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 열거형은 시스템 속성으로만 제한합니다. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 로컬 및 전파 속성을 포함하지만 열거형에서 시스템 속성을 제외합니다. |

수업의 경우:

지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | 열거형이 클래스 정의에서 재정의된 속성으로 제한합니다. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | 열거형 속성을 현재 클래스 정의에서 재정의하고 클래스에 정의된 새 속성으로 제한합니다. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | 플래그가 아닌 `lEnumFlags` 마스크로 값에 적용하여 둘 중 `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` 하나 또는 설정된지 확인합니다. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 열거형은 클래스 자체에서 정의되거나 수정된 속성으로 제한합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 열거형은 기본 클래스에서 상속되는 속성으로 제한합니다. |

인스턴스의 경우:

지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 열거형은 클래스 자체에서 정의되거나 수정된 속성으로 제한합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 열거형은 기본 클래스에서 상속되는 속성으로 제한합니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
