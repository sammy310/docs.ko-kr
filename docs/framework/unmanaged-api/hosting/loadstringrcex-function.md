---
title: LoadStringRCEx 함수
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177977"
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx 함수
HRESULT 값을 지정된 문화어에 적합한 오류 메시지로 변환합니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `lcid`  
 【인】 문화양체 식별자입니다. 기본 문화권을 `lcid` 사용하려면 -1을 전달합니다.  
  
 `iResourceID`  
 【인】 Hresult.  
  
 `szBuffer`  
 【아웃】 성공적으로 완료되면 오류 메시지가 포함된 버퍼입니다.  
  
 `iMax`  
 【인】 오류 메시지 버퍼의 크기입니다.  
  
 `bQuiet`  
 【인】 무시.  
  
 `pcwchUsed`  
 【아웃】 오류 메시지의 길이에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음 값 외에 WinError.h에 정의된 표준 COM 오류 코드를 반환합니다.  
  
|반환 코드|Description|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`szBuffer`null이거나 `iMax` 0(0)입니다.|  
  
## <a name="remarks"></a>설명  
 메서드가 성공적으로 완료되지 `szBuffer` 않으면 빈 문자열이 포함됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [LoadStringRC 함수](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
