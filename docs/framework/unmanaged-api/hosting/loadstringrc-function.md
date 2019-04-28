---
title: LoadStringRC 함수
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f17ecfe683de0739e4e1e063d38836eecf949336
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765312"
---
# <a name="loadstringrc-function"></a>LoadStringRC 함수
HRESULT 값을 현재 스레드의 기본 문화권을 사용 하 여 오류 메시지로 변환 합니다.  
  
 이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `iResourceID`  
 [in] An HRESULT.  
  
 `szBuffer`  
 [out] 성공적으로 완료 되는 오류 메시지를 포함 하는 버퍼입니다.  
  
 `iMax`  
 [in] 오류 메시지 버퍼의 크기입니다.  
  
 `bQuiet`  
 [in] Ignored.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`szBuffer` 이 null 또는 `iMax` 은 영 (0).|  
  
## <a name="remarks"></a>설명  
 메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll 및 Mscorwks.dll 합니다. Mscorwks.dll 대신 MSCorEE.dll을 올바른 버전의.NET Framework 대상 지정 하는 데 사용 합니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [LoadStringRCEx 함수](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
