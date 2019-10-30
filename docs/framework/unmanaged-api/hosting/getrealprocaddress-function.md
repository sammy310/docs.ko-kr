---
title: GetRealProcAddress 함수
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 9dffc3d197b05bb71443aa60c101260daabadadd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136399"
---
# <a name="getrealprocaddress-function"></a>GetRealProcAddress 함수
최신 버전의 CLR (공용 언어 런타임)에서 내보낸 지정 된 함수의 주소를 가져옵니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwszProcName`  
 진행 함수의 이름입니다.  
  
 `ppv`  
 제한이 함수 주소에 대 한 포인터를 수신 하는 위치입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 Winerror.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드와 CorError. h에 정의 된 다음 값을 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`ppv`가 잘못된 경우|  
|CLR_E_SHIM_RUNTIMEEXPORT|함수는 런타임에서 내보내지 않습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
