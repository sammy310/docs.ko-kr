---
title: ICorDebugRemote::CreateProcessEx 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
ms.openlocfilehash: 37bf800f27754d1bf80aece962b7cbb85b1cbedc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712185"
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx 메서드

디버거의 원격 컴퓨터에서 프로세스를 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pRemoteTarget`  
 진행 [ICorDebugRemoteTarget 인터페이스](icordebugremotetarget-interface.md)에 대 한 포인터입니다. 프로세스가 시작 되는 원격 컴퓨터를 확인 하는 데 사용 됩니다.  
  
 `lpApplicationName`  
 진행 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 모듈은 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.  
  
 `lpCommandLine`  
 진행 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 `lpProcessAttributes`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `lpThreadAttributes`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `bInheritHandles`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `dwCreationFlags`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `lpEnvironment`  
 진행 새 프로세스에 대 한 환경 블록에 대 한 포인터입니다.  
  
 `lpCurrentDirectory`  
 진행 프로세스의 현재 디렉터리에 대 한 전체 경로를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수가 null 이면 새 프로세스는 호출 프로세스와 동일한 현재 드라이브 및 디렉터리를 갖게 됩니다.  
  
 `lpStartupInfo`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `lpProcessInformation`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `debuggingFlags`  
 진행 원격 디버깅에 사용 되지 않습니다.  
  
 `ppProcess`  
 제한이 프로세스를 나타내는 "ICorDebugProcess Interface" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  

 S_OK  
 원격 컴퓨터에서 프로세스를 시작 하 고 디버깅을 위해 "ICorDebugProcess Interface"를 반환 했습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 원격 컴퓨터에서 프로세스를 시작 하 고 디버깅을 위해 "ICorDebugProcess Interface"를 반환할 수 없습니다.  
  
## <a name="remarks"></a>설명  

 Silverlight에서는 혼합 모드 디버깅이 지원 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug .idl  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>참조

- [ICorDebugRemote 인터페이스](icordebugremote-interface.md)
- [ICorDebug 인터페이스](icordebug-interface.md)

- [디버깅 인터페이스](debugging-interfaces.md)
