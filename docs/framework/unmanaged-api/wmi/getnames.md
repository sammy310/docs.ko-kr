---
title: GetNames 함수 (관리 되지 않는 API 참조)
description: GetNames 함수 개체의 속성 이름을 검색합니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f664edf29e5d2f9ec4e523aa7f7b204cf999e01b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61724085"
---
# <a name="getnames-function"></a>GetNames 함수
개체 속성의 하위 집합 또는 모든 이름을 검색합니다. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
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
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`wszQualifierName`  
[in] 유효한 포인터 `LPCWSTR` 필터의 일부로 작동 하는 한정자 이름을 지정 하는 합니다. 자세한 내용은 참조는 [주의](#remarks) 섹션입니다. 이 매개 변수는 `null`일 수 있습니다. 

`lFlags`  
[in] 비트 필드의 조합입니다. 자세한 내용은 참조는 [주의](#remarks) 섹션입니다.

`pQualifierValue`   
[in] 유효한 포인터 `VARIANT` 구조 필터 값으로 초기화 합니다. 이 매개 변수는 `null`일 수 있습니다. 

`pstrNames`  
[out] `SAFEARRAY` 속성 이름이 포함 된 구조입니다. 항목에서이 매개 변수 여야에 대 한 포인터 `null`합니다. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다. 

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 잘못 된 경우 또는 플래그 및 매개 변수는 잘못 된 조합이 지정 되었습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) 메서드.

명명 된 반환 매개 변수 및 플래그의 조합으로 제어 됩니다. 예를 들어, 모든 속성의 이름 또는 키 속성의 이름만 함수가 반환할 수 있습니다.  기본 필터에 지정 된 된 `lFlags` 매개 변수 및 다른 매개 변수를 그에 따라 달라 집니다.

플래그 값 `lFlags` 는 비트 필드

로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 비트 필드는 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.  다른 그룹의 모든 플래그를 사용 하 여 각 그룹에서 하나 이상의 플래그를 결합할 수 있습니다. 그러나 동일한 그룹의 플래그는 함께 사용할 수 없습니다. 

| 그룹 1 플래그 |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | 모든 속성 이름을 반환 합니다. `strQualifierName` 및 `pQualifierVal` 사용 되지 않습니다. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | 지정 된 이름의 한정자가 있는 속성만 반환 합니다 `strQualifierName` 매개 변수입니다. 이 플래그를 사용 하는 경우를 지정 해야 `strQualifierName`합니다. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  지정 된 이름의 한정자를 갖지 않는 속성만 반환 합니다 `strQualifierName` 매개 변수입니다. 이 플래그를 사용 하는 경우를 지정 해야 `strQualifierName`합니다. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | 하 여 지정 된 이름의 한정자가 하는 속성만 반환 합니다 `wszQualifierName` 매개 변수 값에 지정 된 동일한 수도 있고는 `pQualifierVal` 구조입니다. 이 플래그를 사용 하는 경우 둘 다 지정 해야 하는 `wszQualifierName` 및 `pQualifierValue`합니다. |

| 그룹 2 플래그 |값  |설명  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 키를 정의 하는 속성의 이름만 반환 합니다. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 반환 속성 이름만 개체 참조입니다. |

| 그룹 3 플래그 |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 가장 많이 파생 된 클래스에 속하는 속성 이름만 반환 합니다. 부모 클래스에서 속성을 제외 합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 부모 클래스에 속하는 속성 이름만 반환 합니다. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 시스템 속성의 이름만 반환 합니다. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 비 시스템 속성의 이름만 반환 합니다. |

함수는 항상 새 할당 `SAFEARRAY` 반환 `WBEM_S_NO_ERROR`, 및 `pstrNames` 항상 가리키도록로 설정 됩니다. 속성이 지정 된 필터와 일치 하는 경우 반환된 된 배열의 0 요소를 포함할 수 있습니다. 함수가 아닌 다른 값을 반환 하는 경우 `WBM_S_NO_ERROR`, 새 `SAFEARRAY` 구조 반환 되지 않습니다.
 
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
