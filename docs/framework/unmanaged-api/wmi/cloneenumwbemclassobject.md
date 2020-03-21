---
title: 클론에넘WbemClassObject 함수(관리되지 않는 API 참조)
description: CloneEnumWbemClassObject 함수는 열거자의 논리적 복사본을 만듭니다.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175020"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject 함수
열거형의 현재 위치를 유지하면서 열거자의 논리적 복사본을 만듭니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a>매개 변수

`ppEnum`\
【아웃】 새 [IEnumWbemClassObject에](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)대한 포인터를 받습니다.

`authLevel`\
【인】 권한 부여 수준입니다.

`impLevel`\
【인】 가장 수준입니다.

`pCurrentEnumWbemClassObject`\
【아웃】 복제할 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) 인스턴스에 대한 포인터입니다.

`strUser`\
【인】 사용자 이름입니다. 자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.

`strPassword`\
【인】 암호입니다. 자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.

`strAuthority`\
【인】 사용자의 도메인 이름입니다. 자세한 내용은 [ConnectServerWmi](connectserverwmi.md) 기능을 참조하십시오.

## <a name="return-value"></a>반환 값

이 함수에서 반환되는 다음 값은 *WbemCli.h* 헤더 파일에 정의되거나 코드에서 상수로 정의할 수 있습니다.

|지속적임  |값  |Description  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 일반적인 오류가 발생했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못되었습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 메모리가 부족하여 작업을 완료할 수 있습니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스와 WMI 간의 원격 프로시저 호출(RPC) 연결이 실패했습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공했습니다.  |

## <a name="remarks"></a>설명

이 함수는 [IEnumWbemClassObject::복제](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) 메서드에 대한 호출을 래핑합니다.

이 메서드는 "최선의 노력" 복사본만 만듭니다. 많은 CIM 개체의 동적 특성으로 인해 새 열거자가 원본 열거기와 동일한 개체 집합을 열거하지 않을 수 있습니다.

함수 호출에 실패하면 [GetErrorInfo](geterrorinfo.md) 함수를 호출하여 추가 오류 정보를 얻을 수 있습니다.

## <a name="example"></a>예제

예를 들어 [IEnumWbemClassObject::복제](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) 메서드를 참조하십시오.

## <a name="requirements"></a>요구 사항
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

 **헤더:** WMINet_Utils.idl

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
