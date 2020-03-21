---
title: GetCORSystemDirectory 함수
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178200"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory 함수
프로세스에 로드되는 공통 언어 런타임(CLR)의 설치 디렉토리를 반환합니다. 설치 디렉토리는 "c:\windows\microsoft.net\framework\v1.0.3705"와 같은 자격을 갖추게 됩니다.  
  
 이 함수는 더 이상 사용되지 않습니다. .NET 프레임워크 4에 제공된 [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) 메서드로 대체됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>매개 변수  
 `pbuffer`  
 【아웃】 런타임이 프로세스에 로드된 런타임에 대해 설치 디렉터리의 정규화된 이름을 포함하는 문자열을 반환하는 버퍼입니다. 런타임이 아직 프로세스에 로드되지 않은 경우 함수는 컴퓨터에 설치된 최신 버전의 런타임에 대한 적절한 디렉터리 정보를 반환합니다.  
  
 `cchBuffer`  
 【인】 의 크기(바이트)입니다. `pbuffer`  
  
 `dwLength`  
 【아웃】 에서 반환된 문자 `pbuffer`수입니다.  
  
## <a name="remarks"></a>설명  
  
> [!CAUTION]
> CLR의 버전 4를 실행하는 프로세스에서는 이 함수를 사용하지 마십시오. 컴퓨터에 이전 버전의 CLR이 설치된 경우 이 함수는 해당 버전에 대한 설치 디렉터리를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MSCorE.h  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
