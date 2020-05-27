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
ms.openlocfilehash: 4b270c36bdbea9c8d81915eba424cae1054ce7d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008536"
---
# <a name="loadlibraryshim-function"></a>LoadLibraryShim 함수
.NET Framework 재배포 가능 패키지에 포함 된 DLL의 지정 된 버전을 로드 합니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다. 대신 [ICLRRuntimeInfo:: LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) 메서드를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `szDllName`  
 진행 .NET Framework 라이브러리에서 로드할 DLL의 이름을 나타내는 0으로 끝나는 문자열입니다.  
  
 `szVersion`  
 진행 로드할 DLL의 버전을 나타내는 0으로 끝나는 문자열입니다. `szVersion`가 null 이면 로드 하도록 선택한 버전이 버전 4 보다 작은 최신 버전의 지정 된 DLL입니다. 즉,가 null 이면 버전 4 보다 크거나 같은 모든 버전이 무시 되 `szVersion` 고 버전 4 보다 작은 버전이 설치 되어 있으면 DLL이 로드 되지 않습니다. 이는 .NET Framework 4 설치가 기존 응용 프로그램 또는 구성 요소에 영향을 주지 않도록 하기 위한 것입니다. CLR 팀 블로그에서 [-Proc SxS 및 Migration 빠른 시작](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) 항목을 참조 하세요.  
  
 `pvReserved`  
 다음에 사용하도록 예약됩니다.  
  
 `phModDll`  
 제한이 모듈의 핸들에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.  
  
|반환 코드|Description|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|CLR_E_SHIM_RUNTIMELOAD|로드 `szDllName` 하려면 clr (공용 언어 런타임)을 로드 해야 하며 clr의 필수 버전을 로드할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 함수는 .NET Framework 재배포 가능 패키지에 포함 된 Dll을 로드 하는 데 사용 됩니다. 사용자가 생성 한 Dll은 로드 하지 않습니다.  
  
> [!NOTE]
> .NET Framework 버전 2.0부터 Fusion .dll을 로드 하면 CLR이 로드 됩니다. 이는 Fusion의 함수는 이제 런타임이 제공 하는 구현이 있는 래퍼 이기 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
