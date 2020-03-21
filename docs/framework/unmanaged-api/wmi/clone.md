---
title: 복제 함수(관리되지 않는 API 참조)
description: 복제 함수는 현재 개체의 전체 복제인 새 개체를 반환합니다.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176853"
---
# <a name="clone-function"></a>Clone 함수
현재 개체의 전체 복제본인 새 개체를 반환합니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`ppCopy`  
【아웃】 의 완전한 외로운 새 `ptr`개체입니다. 이 인수는 `null` 현재 개체의 복사본을 받는 경우일 수 없습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `null`매개 변수로 지정되었으며 이 사용에서는 합법적이지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 개체를 복제할 수 있는 메모리가 부족합니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::복제](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드에 대한 호출을 래핑합니다.

복제된 개체는 참조 수가 1인 COM 개체입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
