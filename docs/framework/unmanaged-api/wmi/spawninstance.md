---
title: 스폰인스턴스 함수(관리되지 않는 API 참조)
description: SpawnInstance 함수는 클래스의 새 인스턴스를 만듭니다.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176723"
---
# <a name="spawninstance-function"></a>SpawnInstance 함수
클래스의 새 인스턴스를 만듭니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스에 대한 포인터입니다.

`lFlags`  
[in] 예약되어 있습니다. 이 매개변수는 0이어야 합니다.

`ppNewInstance`  
【아웃】 클래스의 새 인스턴스에 대한 포인터를 받습니다. 오류가 발생하면 새 개체가 반환되지 않고 `ppNewInstance` 수정되지 않은 상태로 남아 있습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr`유효한 클래스 정의이며 새 인스턴스를 생성할 수 없습니다. 불완전하거나 [PutClassWmi를](putclasswmi.md)호출하여 Windows 관리에 등록되지 않았습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass`은 `null`입니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |
  
## <a name="remarks"></a>설명

이 함수는 [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) 메서드에 대한 호출을 래핑합니다.

`ptr`Windows 관리에서 가져온 클래스 정의여야 합니다. 인스턴스에서 인스턴스를 스폰하는 것은 지원되지만 반환된 인스턴스는 비어 있습니다.) 그런 다음 이 클래스 정의를 사용하여 새 인스턴스를 만듭니다. Windows 관리에 인스턴스를 작성하려면 [PutInstanceWmi](putinstancewmi.md) 함수를 호출해야 합니다.

자동으로 반환되는 `ppNewClass` 새 개체는 현재 개체의 하위 클래스가 됩니다. 이 동작은 재정의할 수 없습니다. 하위 클래스(파생 클래스)를 만들 수 있는 다른 방법은 없습니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
