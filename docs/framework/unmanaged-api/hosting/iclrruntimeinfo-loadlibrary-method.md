---
description: '자세히 알아보기: ICLRRuntimeInfo:: LoadLibrary 메서드'
title: ICLRRuntimeInfo::LoadLibrary 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 47557934868c7c1b68b23bf4eded0e90705d7252
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785057"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>ICLRRuntimeInfo::LoadLibrary 메서드

[ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스로 표시 되는 CLR (공용 언어 런타임)에서 .NET Framework 라이브러리를 로드 합니다.  
  
 이 메서드는 [LoadLibraryShim](loadlibraryshim-function.md) 함수를 대체 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pwzDllName`  
 진행 로드할 어셈블리의 이름입니다.  
  
 `phndModule`  
 제한이 로드 된 어셈블리에 대 한 핸들입니다.  
  
## <a name="return-value"></a>Return Value  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pwzDllName` 또는 `phndModule`가 null입니다.|  
|E_OUTOFMEMORY|메모리가 부족 하 여 요청을 처리할 수 없습니다.|  
  
## <a name="remarks"></a>설명  

 이 메서드는 .NET Framework 재배포 가능 패키지에 포함 된 Dll만 로드 합니다. 사용자가 생성 한 어셈블리를 로드할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRRuntimeInfo 인터페이스](iclrruntimeinfo-interface.md)
- [호스팅 인터페이스](hosting-interfaces.md)
- [호스팅](index.md)
