---
title: LoadLibraryShim 함수
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32aee404891bfad1aed2abc9ad84e43bcd002df5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084572"
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim 함수
지정된 된 버전의.NET Framework 재배포 가능 패키지에 포함 된 DLL 로드 합니다.  
  
 이 함수에서 사용 중단에 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 사용 된 [iclrruntimeinfo:: Loadlibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) 메서드 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szDllName`  
 [in] .NET Framework 라이브러리에서 로드할 DLL의 이름을 나타내는 0으로 끝나는 문자열입니다.  
  
 `szVersion`  
 [in] 로드할 DLL의 버전을 나타내는 0으로 끝나는 문자열입니다. 경우 `szVersion` 가 null 인 로드 4 버전 보다 낮은 경우 지정된 된 DLL의 최신 버전에 대 한 선택한 버전입니다. 즉, 버전 4 보다 크거나 같은 버전을 모두 무시 됩니다 `szVersion` 가 null DLL을 로드 하지 없는 보다 낮은 버전이 버전 4가 설치 되어 있습니다. 설치를 확인 하는 것이 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 기존 응용 프로그램 또는 구성 요소에는 영향을 주지 않습니다. 항목을 참조 하세요 [In-proc SxS 및 마이그레이션 퀵스타트](https://go.microsoft.com/fwlink/?LinkId=200329) CLR 팀 블로그의 합니다.  
  
 `pvReserved`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `phModDll`  
 [out] 모듈의 핸들에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|CLR_E_SHIM_RUNTIMELOAD|로드 `szDllName` 로드 된 CLR (공용 언어 런타임), 및 필요한 버전의 CLR 로드할 수 없습니다 필요 합니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는.NET Framework 재배포 가능 패키지에 포함 된 Dll을 로드 하려고 사용 됩니다. 사용자에서 생성 된 Dll를 로드 하지 않습니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0 부터는 로드할 CLR 하면 Fusion.dll를 로드 합니다. Fusion.dll 함수 구현을 런타임에서 제공 하는 래퍼 됩니다 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** MSCorEE.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [사용되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
