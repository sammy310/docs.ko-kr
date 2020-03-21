---
title: GetNames 함수(관리되지 않는 API 참조)
description: GetNames 함수는 개체의 속성 이름을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174955"
---
# <a name="getnames-function"></a>GetNames 함수
개체 속성의 하위 집합 또는 모든 이름을 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`wszQualifierName`  
【인】 필터의 일부로 `LPCWSTR` 작동하는 한정자 이름을 지정하는 유효한 포인터입니다. 자세한 내용은 [비고](#remarks) 섹션을 참조하십시오. 이 매개 변수는 `null`일 수 있습니다.

`lFlags`  
【인】 비트 필드의 조합입니다. 자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.

`pQualifierValue`【인】 필터 값으로 `VARIANT` 초기화된 유효한 구조에 대한 포인터입니다. 이 매개 변수는 `null`일 수 있습니다.

`pstrNames`  
【아웃】 속성 `SAFEARRAY` 이름을 포함하는 구조입니다. 항목에서 이 매개 변수는 항상 `null`에 대한 포인터여야 합니다. 자세한 내용은 [비고](#remarks) 섹션을 참조하십시오.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 유효하지 않거나 플래그와 매개 변수의 잘못된 조합이 지정되었습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) 메서드에 대 한 호출을 래핑합니다.

반환된 명명된 플래그와 매개 변수의 조합에 의해 제어됩니다. 예를 들어 함수는 모든 속성의 이름 또는 키 속성의 이름만 반환할 수 있습니다.  기본 필터는 매개 `lFlags` 변수에 지정되고 다른 매개 변수는 매개 변수에 따라 다릅니다.

플래그 `lFlags` 값은 비트 필드입니다.

`lEnumFlags` 인수로 전달될 수 있는 플래그는 *WbemCli.h* 헤더 파일에 정의된 비트 필드이거나 코드에서 상수로 정의할 수 있습니다.  각 그룹의 한 플래그를 다른 그룹의 모든 플래그와 결합할 수 있습니다. 그러나 동일한 그룹의 플래그는 상호 배타적입니다.

| 그룹 1 플래그 |값  |Description  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | 모든 속성 이름을 반환합니다. `strQualifierName``pQualifierVal` 사용되지 않습니다. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | 매개 변수에 의해 지정된 이름의 한정자가 있는 속성만 반환합니다. `strQualifierName` 이 플래그를 사용하는 경우 `strQualifierName`을 지정해야 합니다. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  매개 변수에 의해 지정된 이름의 한정자가 `strQualifierName` 없는 속성만 반환합니다. 이 플래그를 사용하는 경우 `strQualifierName`을 지정해야 합니다. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | `wszQualifierName` 매개 변수에 의해 지정된 이름의 한정자가 있고 `pQualifierVal` 구조가 지정한 값과 동일한 값을 가진 속성만 반환합니다. 이 플래그를 사용하는 경우 a와 `wszQualifierName` 를 `pQualifierValue`모두 지정해야 합니다. |

| 그룹 2 플래그 |값  |Description  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 키를 정의하는 속성 이름만 반환합니다. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 개체 참조인 속성 이름만 반환합니다. |

| 그룹 3 플래그 |값  |Description  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 가장 파생된 클래스에 속하는 속성 이름만 반환합니다. 상위 클래스에서 속성을 제외합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 상위 클래스에 속하는 속성 이름만 반환합니다. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 시스템 속성의 이름만 반환합니다. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 비시스템 속성의 이름만 반환합니다. |

함수는 반환하는 경우 `SAFEARRAY` `WBEM_S_NO_ERROR`항상 새 를 `pstrNames` 할당하고 항상 가리키도록 설정됩니다. 반환된 배열에는 지정된 필터와 일치하는 속성이 없는 경우 0개의 요소가 있을 수 있습니다. 함수가 `WBM_S_NO_ERROR`이외의 값을 반환하면 새 `SAFEARRAY` 구조가 반환되지 않습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
