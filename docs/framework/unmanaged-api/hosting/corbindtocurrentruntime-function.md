---
title: CorBindToCurrentRuntime 함수
ms.date: 03/30/2017
api_name:
- CorBindToCurrentRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- HeaderDef
f1_keywords:
- CorBindToCurrentRuntime
helpviewer_keywords:
- CorBindToCurrentRuntime function [.NET Framework hosting]
ms.assetid: 6105c13e-d9cd-44d2-a95a-924e042830c7
topic_type:
- apiref
ms.openlocfilehash: 77a0a8f58c11673a1958d837b4c3a21a05754c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138327"
---
# <a name="corbindtocurrentruntime-function"></a>CorBindToCurrentRuntime 함수
XML 파일에 저장 된 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다. XML 파일의 형식은 표준 응용 프로그램 구성 파일 다음에 모델링 됩니다. 구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다. [프로세스에 공용 언어 런타임 로드](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/01918c6x(v=vs.100))를 참조 하세요.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CorBindToCurrentRuntime (  
    [in]  LPCWSTR   pwszFileName,  
    [in]  REFCLSID  rclsid,  
    [in]  REFIID    riid,  
    [out] LPVOID    *ppv  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwszFileName`  
 진행 로드할 CLR 버전을 지정 하는 응용 프로그램 구성 파일의 이름입니다. 파일 이름이 정규화 되지 않은 경우 호출을 수행 하는 실행 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.  
  
 로드할 런타임 버전은 구성 파일의 [\<requiredRuntime >](../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 요소의 version 특성에 설명 되어 있습니다.  
  
 버전을 지정 하지 않거나 `<requiredRuntime>` 요소를 찾을 수 없는 경우 컴퓨터에 설치 된 CLR의 최신 버전이 로드 됩니다.  
  
 `rclsid`  
 진행 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다. 지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.  
  
 `riid`  
 진행 요청 하는 인터페이스의 `IID`입니다. 지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.  
  
 `ppv`  
 제한이 반환 된 인터페이스 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** Mscoree.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [CorBindToRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
