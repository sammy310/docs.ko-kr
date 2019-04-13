---
title: CorBindToRuntimeByCfg 함수
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbba208296dd2099c9da58c81ff66fddc78fdc86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093821"
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg 함수
XML 파일에서 읽은 버전 정보를 사용 하 여 프로세스에는 CLR (공용 언어 런타임)을 로드 합니다.  
  
 이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,   
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pCfgStream`  
 [in] 에 대 한 포인터는 `IStream` XML 파일을 읽는 개체입니다.  
  
 `reserved`  
 [in] 사용 하도록 예약 합니다. 값으로 0 (영)을 사용 합니다.  
  
 `startupFlags`  
 [in] 값을 [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) CLR의 시작 동작을 지정 하는 열거형입니다.  
  
 `rclsid`  
 [in] 합니다 `CLSID` 중 하나를 구현 하는 coclass의 합니다 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다. 지원 되는 값은 CLSID_CorRuntimeHost CLSID_CLRRuntimeHost입니다.  
  
 `riid`  
 [in] 합니다 `IID` 중 합니다 `ICorRuntimeHost` 또는 `ICLRRuntimeHost` 인터페이스입니다. 지원 되는 값은 IID_ICorRuntimeHost IID_ICLRRuntimeHost입니다.  
  
 `ppv`  
 [out] 반환 되는 인터페이스의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 XML 파일의 형식은 표준 응용 프로그램 구성 파일을 따라 모델링 됩니다. XML 파일에 대 한 자세한 내용은 참조 하세요. [구성 파일 스키마](../../../../docs/framework/configure-apps/file-schema/index.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [CorBindToRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
