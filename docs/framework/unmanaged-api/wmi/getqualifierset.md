---
title: GetQualifierSet 함수(관리되지 않는 API 참조)
description: GetQualifierSet 함수는 클래스 또는 인스턴스에 대한 한정자 집합을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176775"
---
# <a name="getqualifierset-function"></a>GetQualifierSet 함수
클래스 인스턴스 또는 클래스 정의에 대한 한정자 집합을 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`ppQualSet`  
【아웃】 클래스 개체의 한정자에 액세스할 수 있는 인터페이스 포인터를 받습니다. `ppQualSet`가 `null`이 될 수 없는 경우 오류가 발생하면 새 개체가 반환되지 않고 포인터가 수정되지 않은 상태로 유지됩니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 메서드가 없습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수는 `null`. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) 메서드에 대한 호출을 래핑합니다.

[IWbemQualifierSet 포인터를](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 사용하면 호출자가 이러한 한정자를 추가, 편집 또는 삭제할 수 있습니다. 이러한 추가, 편집 또는 삭제된 한정자는 전체 인스턴스 또는 클래스 정의에 적용됩니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
