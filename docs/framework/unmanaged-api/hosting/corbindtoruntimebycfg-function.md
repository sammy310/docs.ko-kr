---
description: '자세히 알아보기: CorBindToRuntimeByCfg 함수'
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
ms.openlocfilehash: c1acf6a8f1d8637bc2d6cd180016ff51cf500107
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790076"
---
# <a name="corbindtoruntimebycfg-function"></a>CorBindToRuntimeByCfg 함수

XML 파일에서 읽은 버전 정보를 사용 하 여 CLR (공용 언어 런타임)을 프로세스로 로드 합니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
 진행 XML 파일을 읽는 개체에 대 한 포인터 `IStream` 입니다.  
  
 `reserved`  
 진행 나중에 사용 하도록 예약 되어 있습니다. 값으로 0을 사용 합니다.  
  
 `startupFlags`  
 진행 CLR의 시작 동작을 지정 하는 [STARTUP_FLAGS](startup-flags-enumeration.md) 열거형의 값입니다.  
  
 `rclsid`  
 진행 [ICorRuntimeHost](icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](iclrruntimehost-interface.md) 인터페이스를 구현 하는 coclass 의 `CLSID`입니다. 지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.  
  
 `riid`  
 진행 `IID` 또는 인터페이스의입니다 `ICorRuntimeHost` `ICLRRuntimeHost` . 지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.  
  
 `ppv`  
 제한이 반환 된 인터페이스의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 XML 파일의 형식은 표준 응용 프로그램 구성 파일 다음에 모델링 됩니다. XML 파일에 대 한 자세한 내용은 [구성 파일 스키마](../../configure-apps/file-schema/index.md)를 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [CorBindToCurrentRuntime 함수](corbindtocurrentruntime-function.md)
- [CorBindToRuntime 함수](corbindtoruntime-function.md)
- [CorBindToRuntimeEx 함수](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost 함수](corbindtoruntimehost-function.md)
- [ICorRuntimeHost 인터페이스](icorruntimehost-interface.md)
- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
