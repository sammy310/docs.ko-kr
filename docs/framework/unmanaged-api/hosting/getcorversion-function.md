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
ms.openlocfilehash: e7ef3f300c8cfa0c275d15913e171abe09385eea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681212"
---
# <a name="getcorversion-function"></a>GetCORVersion 함수

현재 프로세스에서 실행 중인 CLR (공용 언어 런타임)의 버전 번호를 반환 합니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
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
 CLR이 프로세스에 현재 로드 된 런타임 버전을 지정 하는 문자열을 반환 하는 버퍼에 대 한 포인터입니다. 반환 된 문자열은 [CorBindToRuntimeEx](corbindtoruntimeex-function.md)에 전달 된 문자열과 동일한 형식을 사용 합니다 (예: "v 1.0.1216"). 런타임이 아직 프로세스에 로드 되지 않은 경우이 함수는 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.  
  
 `cchBuffer`  
 에서 보유할 수 있는 문자 수입니다 `WCHAR` `pbuffer` .  
  
 `dwLength`  
 에 실제로 반환 된 문자 수에 대 한 포인터 `pbuffer` 입니다. `pbuffer`가 null 포인터인 경우 런타임은 E_POINTER을 반환 합니다. 문자 수가의 길이 보다 큰 경우 `pbuffer` 런타임에서는 ERROR_INSUFFICIENT_BUFFER을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
