---
title: ICLRDebuggingLibraryProvider::ProvideLibrary 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd1038fdc8b22b99e1c8c7b753b46b9ce877355
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496445"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary 메서드
라이브러리 공급자 콜백 인터페이스를 공용 언어 런타임 (CLR) 버전별 디버깅 라이브러리 있고에 로드 된 요청 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pwszFilename`  
 [in] 요청 되는 모듈의 이름입니다.  
  
 `dwTimestamp`  
 [in] PE 파일의 coff 파일에에서 저장 된 날짜 타임 스탬프입니다.  
  
 `pLibraryProvider`  
 [in] `SizeOfImage` 필드 COFF 선택적 파일 헤더의 PE 파일에 저장 합니다.  
  
 `hModule`  
 [out] 요청된 된 모듈에 대 한 핸들입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
 `ProvideLibrary` 디버거를 mscordbi.dll mscordacwks.dll 등 특정 CLR 파일 디버깅에 필요한 모듈을 제공할 수 있습니다. 모듈 핸들에 대 한 호출 될 때까지 유효 해야 합니다 [iclrdebugging:: Canunloadnow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) 는 해제할 수 있습니다 이며 이때 핸들을 해제 해야 하는 호출자의 메서드를 나타냅니다.  
  
 디버거를 찾거나 조달 디버깅 모듈에 사용 가능한 모든 수단을 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  이 기능을 사용 하면 API 호출자가 실행 파일 및 악의적인 코드가 포함 된 모듈을 제공 합니다. 보안 조치로, 호출자에 게 사용 하지 않아야 `ProvideLibrary` 자체를 실행 하는 코드를 배포 합니다.  
>   
>  심각한 보안 문제가 발견 되 면, mscordbi.dll 등 mscordacwks.dll, 이미 출시 된 라이브러리에 파일의 잘못 된 버전을 인식 하도록 shim은 패치할 수 있습니다. Shim 수 되어 파일의 패치 버전에 대 한 요청을 발급 하 고 모든 요청에 대 한 응답에서 제공 하는 경우 잘못 된 버전을 거부 합니다. 사용자가 새 버전의 shim 패치 하는 경우에 발생할 수 있습니다. 패치가 적용 되지 않은 버전 취약 한 상태로 유지 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고자료
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
