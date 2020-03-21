---
title: 파생 클래스 함수(관리되지 않는 API 참조)
description: SpawnDerivedClass 함수는 개체에서 파생되는 새 개체를 만듭니다.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174851"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass 함수
지정된 개체에서 새로 파생된 클래스 개체를 만듭니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`lFlags`  
[in] 예약되어 있습니다. 이 매개변수는 0이어야 합니다.

`ppNewClass`  
【아웃】 새 클래스 정의 개체에 대한 포인터를 받습니다. 오류가 발생하면 새 개체가 반환되지 않고 `ppNewClass` 수정되지 않은 상태로 남아 있습니다. 해당 값은 `null`할 수 없습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | 인스턴스에서 클래스를 스폰하는 것과 같은 잘못된 작업이 요청되었습니다. |
| `WBEM_E_INCOMPLETE_CLASS` | 소스 클래스가 완전히 정의되거나 Windows Management에 등록되지 않았기 때문에 새 파생 클래스는 허용되지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass`은 `null`입니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드에 대한 호출을 래핑합니다.

`ptr`은 생성된 개체의 상위 클래스가 되는 클래스 정의여야 합니다. 반환된 개체는 현재 개체의 하위 클래스가 됩니다.

자동으로 반환되는 `ppNewClass` 새 개체는 현재 개체의 하위 클래스가 됩니다. 이 동작은 재정의할 수 없습니다. 하위 클래스(파생 클래스)를 만들 수 있는 다른 방법은 없습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
