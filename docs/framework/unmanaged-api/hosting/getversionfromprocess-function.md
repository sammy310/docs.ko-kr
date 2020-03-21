---
title: GetVersionFromProcess 함수
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178125"
---
# <a name="getversionfromprocess-function"></a>GetVersionFromProcess 함수
지정된 프로세스 핸들과 연결된 공통 언어 런타임(CLR)의 버전 번호를 가져옵니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `hProcess`  
 【인】 프로세스에 대한 핸들입니다.  
  
 `pVersion`  
 【아웃】 메서드가 성공적으로 완료되면 버전 번호 문자열이 포함된 버퍼입니다.  
  
 `cchBuffer`  
 【인】 버전 버퍼의 길이입니다.  
  
 `pdwLength`  
 【아웃】 버전 번호 문자열의 길이에 대한 포인터입니다.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음 값 외에 WinError.h에 정의된 표준 구성 요소 개체 모델(COM) 오류 코드를 반환합니다.  
  
|반환 코드|Description|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`pVersion`null이며 `cchBuffer` null이 아니거나 그 반대의 경우도 마찬가지입니다.<br /><br /> 또는<br /><br /> `hProcess`프로세스에 대한 올바른 핸들이 아닙니다.<br /><br /> 또는<br /><br /> CLR이 로드되지 않았습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`cchBuffer`은 null 또는 버전 문자열의 길이보다 작습니다.|  
|E_NOTIMPL|이 방법은 마이크로 소프트 윈도우 95, 마이크로 소프트 윈도우 98, 또는 마이크로 소프트 윈도우 밀레니엄 에디션 운영 체제에서 사용할 수 없습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [GetRequestedRuntimeInfo 함수](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [GetRequestedRuntimeVersion 함수](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
