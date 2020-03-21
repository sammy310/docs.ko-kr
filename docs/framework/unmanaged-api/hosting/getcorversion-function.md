---
title: GetCORVersion 함수
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178187"
---
# <a name="getcorversion-function"></a>GetCORVersion 함수
현재 프로세스에서 실행 중인 공통 언어 런타임(CLR)의 버전 번호를 반환합니다.  
  
 이 함수는 .NET 프레임워크 4에서 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `pbuffer`  
 CLR이 현재 프로세스에 로드된 런타임 버전을 지정하는 문자열을 반환하는 버퍼에 대한 포인터입니다. 반환된 문자열은 [CorBindToRuntimeEx(예:](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)"v1.0.1216")에 전달된 문자열과 동일한 형식을 취합니다. 런타임이 아직 프로세스에 로드되지 않은 경우 함수는 컴퓨터에 설치된 최신 버전의 런타임에 대한 적절한 디렉터리 정보를 반환합니다.  
  
 `cchBuffer`  
 에서 보유할`WCHAR`수 있는 문자 수입니다. `pbuffer`  
  
 `dwLength`  
 실제로 반환된 문자 수에 `pbuffer`대한 포인터입니다. null `pbuffer` 포인터인 경우 런타임은 E_POINTER 반환합니다. 문자 수가 클수록 `pbuffer` 길이가 ERROR_INSUFFICIENT_BUFFER 반환됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
