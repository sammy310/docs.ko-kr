---
title: GetCurrent아파트유형 함수(관리되지 않는 API 참조)
description: GetCurrentApartmentType 함수는 호출자를 실행 하는 아파트의 형식을 검색합니다.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176827"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType 함수
호출자가 실행 중인 아파트의 유형을 검색합니다.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
【인】 이 매개 변수는 사용되지 않습니다.

`ptr`  
【인】 [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) 인스턴스에 대한 포인터입니다.

`aptType`  
【아웃】 호출자의 아파트를 나타내는 [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) 열거 값에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

|지속적임  |값  |Description  |
|---------|---------|---------|
| `S_OK` | 0 | 함수가 성공적으로 완료되었습니다. |
| `E_FAIL` | 0x80000008 | 호출자는 아파트에서 실행되지 않습니다. |
  
## <a name="remarks"></a>설명

이 함수는 [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) 메서드에 대 한 호출을 래핑합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목

- [WMI 및 성능 카운터(관리되지 않는 API 참조)](index.md)
