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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deec4d40270a11b9e48a0ab39504d774314c077c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736195"
---
# <a name="getcorsystemdirectory-function"></a>GetCORSystemDirectory 함수
프로세스에 로드 되는 공용 언어 런타임 (CLR)의 설치 디렉터리를 반환 합니다. 설치 디렉터리는 정규화 된 이름, 예를 들어, "c:\windows\microsoft.net\framework\v1.0.3705"입니다.  
  
 이 함수는 사용 되지 않습니다. 에 의해 대체 된 [iclrruntimeinfo:: Getruntimedirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) .NET Framework 4에서 제공 하는 메서드.  
  
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
 [out] 런타임을 프로세스로 로드 되는 런타임 설치 디렉터리의 정규화 된 이름을 포함 하는 문자열을 반환 하는 버퍼입니다. 런타임 프로세스에 아직 로드 되지가 컴퓨터에 설치 된 런타임의 최신 버전에 대 한 적절 한 디렉터리 정보를 반환 합니다.  
  
 `cchBuffer`  
 [in] 크기 (바이트)의 `pbuffer`합니다.  
  
 `dwLength`  
 [out] 반환 된 문자 수가 `pbuffer`합니다.  
  
## <a name="remarks"></a>설명  
  
> [!CAUTION]
>  CLR 버전 4를 실행 하는 프로세스에서이 함수를 사용 하지 마세요. CLR의 이전 버전 컴퓨터의 설치는 경우이 함수는 해당 버전의 설치 디렉터리를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
