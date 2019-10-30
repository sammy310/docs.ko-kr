---
title: _CorDllMain 함수
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136975"
---
# <a name="_cordllmain-function"></a>\_CorDllMain 함수

CLR (공용 언어 런타임)을 초기화 하 고, DLL 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `hInst`  
 진행 로드 된 모듈의 인스턴스 핸들입니다.  
  
 `dwReason`  
 진행 DLL 진입점 함수가 호출 되는 이유를 나타냅니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다. DLL\_PROCESS_ATTACH, DLL\_스레드\_연결, DLL\_스레드\_연결 또는 DLL\_분리\_프로세스입니다. 이러한 값에 대 한 설명은 Platform SDK의 `DllMain` 설명서를 참조 하세요.  
  
 `lpReserved`  
 진행 사용 되지 않는.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 성공에 `true`를 반환 하 고 오류가 발생 하는 경우 `false` 합니다.  
  
## <a name="remarks"></a>주의  
 이 함수는 DLL 어셈블리에 대 한 운영 체제 로더에 의해 호출 됩니다. 실행 어셈블리의 경우 로더가 [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 함수를 대신 호출 합니다.  
  
 운영 체제 로더는 DLL 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.  
  
운영 체제 로더에서는 `_CorDllMain` 함수를 직접 호출 합니다.
  
 자세한 내용은 [CorValidateImage\_](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
