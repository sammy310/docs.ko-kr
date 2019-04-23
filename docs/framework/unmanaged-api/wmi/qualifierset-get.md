---
title: QualifierSet_Get 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Get 함수는 명명 된 한정자를 가져옵니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0dc76a2732bf9c1e4f3a26fa2d045bfbcd837ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181092"
---
# <a name="qualifiersetget-function"></a>QualifierSet_Get 함수
지정한 명명된 한정자를 가져옵니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`   
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`   
[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.

`wszName`   
[in] 해당 값이 요청 된 한정자의 이름입니다.

`lFlags`   
[in] 예약되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pVal`   
[out] 성공 하면 올바른 형식 및 한정자 값입니다. 함수가 실패 한 경우는 `VARIANT` 가리키는 `pVal` 수정 되지 않습니다. 이 매개 변수가 `null`, 매개 변수는 무시 됩니다.

`plFlavor`   
[out] 요청 된 한정자에 대 한 한정자 flavor 비트를 수신 하는 긴 포인터입니다. 버전 정보는 적절 하지 않으면이 매개 변수 수 `null`입니다. 

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 잘못 되었습니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 한정자가 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료

- [WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
