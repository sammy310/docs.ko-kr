---
title: CloneEnumWbemClassObject 함수 (관리 되지 않는 API 참조)
description: CloneEnumWbemClassObject 함수 열거자의 논리적 복사본을 만듭니다.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac85ed86ea968fa945e07f95db8977a33c5d12a6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367111"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject 함수
열거형의 현재 위치를 유지하면서 열거자의 논리적 복사본을 만듭니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>구문

```
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
[out] 새에 대 한 포인터를 받는 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)합니다.

`authLevel`\
[in] 권한 부여 수준입니다.

`impLevel`\
[in] 가장 수준입니다.

`pCurrentEnumWbemClassObject`\
[out] 에 대 한 포인터를 [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) 인스턴스를 복제할 수 있습니다.

`strUser`\
[in] 사용자 이름입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

`strPassword`\
[in] 암호입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

`strAuthority`\ [in] 사용자의 도메인 이름입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못 되었습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 사용 가능한 메모리가 부족 합니다. 작업을 완료 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) 메서드.

이 메서드는 "최상의" 복사본만을 만듭니다. 많은 CIM 개체의 동적 특성상 있기 새 열거자를 원본 열거자로 동일한 개체 집합을 열거 하지 않습니다.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="example"></a>예제

예를 들어 참조 된 [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) 메서드.

## <a name="requirements"></a>요구 사항
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.

 **헤더:** WMINet_Utils.idl

 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)