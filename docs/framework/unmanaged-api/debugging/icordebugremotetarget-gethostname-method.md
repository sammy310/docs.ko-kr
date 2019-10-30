---
title: ICorDebugRemoteTarget::GetHostName 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: a9a6ca9ae3cdb1c6a7398d08c9f99e3cde125cf6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131907"
---
# <a name="icordebugremotetargetgethostname-method"></a>ICorDebugRemoteTarget::GetHostName 메서드
정규화된 도메인 이름 또는 원격 디버깅 대상 컴퓨터의 IPv4 주소를 반환합니다. IPV6은 이번에 지원되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>매개 변수  
 `cchHostName`  
 진행 `szHostName` 버퍼의 크기 (문자)입니다. 이 매개 변수가 0일 경우 `szHostName`은 null이어야 합니다.  
  
 `pcchHostName`  
 [out] 호스트 이름 또는 IP 주소의 null 종결자를 포함한 문자의 수입니다. 이 매개 변수는 null일 수 있습니다.  
  
 `szHostName`  
 [out] 호스트 이름 또는 IP 주소를 포함하는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 호스트 이름 또는 IP 주소가 성공적으로 반환 되었습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 호스트 이름 또는 IP 주소를 반환할 수 없습니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 디버거 작성기에서 구현합니다. 다중 호출 패러다임을 따라야 합니다. 첫 번째 호출에서 호출자는 `cchHostName` 및 `szHostName`둘 다에 null을 전달 하 고 `pcchHostName`는 필요한 버퍼의 크기를 반환 합니다. 두 번째 호출에서 이전에 반환된 크기는 `cchHostName`에서 전달되고 적절한 크기의 버퍼는 `szHostName`에서 전달됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug .idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참조

- [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
