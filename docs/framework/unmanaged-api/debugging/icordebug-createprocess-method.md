---
title: ICorDebug::CreateProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
ms.openlocfilehash: a69fb861f7c2671a5c26245aa544ee99bcbdb56b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901006"
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess 메서드
디버거를 제어할 때 프로세스 및 해당 기본 스레드를 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `lpApplicationName`  
 진행 시작 된 프로세스에서 실행할 모듈을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 모듈은 호출 프로세스의 보안 컨텍스트에서 실행 됩니다.  
  
 `lpCommandLine`  
 진행 시작 된 프로세스에서 실행할 명령줄을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 응용 프로그램 이름 (예: "SomeApp")은 첫 번째 인수 여야 합니다.  
  
 `lpProcessAttributes`  
 진행 프로세스에 대 한 보안 설명자를 지정 하는 Win32 `SECURITY_ATTRIBUTES` 구조체에 대 한 포인터입니다. `lpProcessAttributes` null 이면 프로세스가 기본 보안 설명자를 가져옵니다.  
  
 `lpThreadAttributes`  
 진행 프로세스의 주 스레드에 대 한 보안 설명자를 지정 하는 Win32 `SECURITY_ATTRIBUTES` 구조체에 대 한 포인터입니다. `lpThreadAttributes`가 null 이면 스레드는 기본 보안 설명자를 가져옵니다.  
  
 `bInheritHandles`  
 진행 호출 프로세스의 각 상속 가능한 핸들이 시작 된 프로세스에서 상속 됨을 나타내거나 핸들이 상속 되지 않음을 나타내는 `false` `true`으로 설정 합니다. 상속 된 핸들에는 원래 핸들과 동일한 값 및 액세스 권한이 있습니다.  
  
 `dwCreationFlags`  
 진행 시작 된 프로세스의 동작 및 우선 순위 클래스를 제어 하는 [Win32 프로세스 생성 플래그](/windows/win32/procthread/process-creation-flags) 의 비트 조합입니다.  
  
 `lpEnvironment`  
 진행 새 프로세스에 대 한 환경 블록에 대 한 포인터입니다.  
  
 `lpCurrentDirectory`  
 진행 프로세스의 현재 디렉터리에 대 한 전체 경로를 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수가 null 이면 새 프로세스는 호출 프로세스와 동일한 현재 드라이브 및 디렉터리를 갖게 됩니다.  
  
 `lpStartupInfo`  
 진행 시작 된 프로세스에 대 한 주 창의 창 스테이션, 바탕 화면, 표준 핸들 및 모양을 지정 하는 Win32 `STARTUPINFOW` 구조체에 대 한 포인터입니다.  
  
 `lpProcessInformation`  
 진행 시작할 프로세스에 대 한 식별 정보를 지정 하는 Win32 `PROCESS_INFORMATION` 구조체에 대 한 포인터입니다.  
  
 `debuggingFlags`  
 진행 디버깅 옵션을 지정 하는 CorDebugCreateProcessFlags 열거형의 값입니다.  
  
 `ppProcess`  
 제한이 프로세스를 나타내는 ICorDebugProcess 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드의 매개 변수는 Win32 `CreateProcess` 메서드와 동일 합니다.  
  
 관리 되지 않는 혼합 모드 디버깅을 사용 하도록 설정 하려면 `dwCreationFlags` &#124; 를 DEBUG_PROCESS DEBUG_ONLY_THIS_PROCESS로 설정 합니다. 관리 되는 디버깅만 사용 하려면 이러한 플래그를 설정 하지 마십시오.  
  
 디버거 및 디버깅할 프로세스 (연결 된 프로세스)가 단일 콘솔을 공유 하 고 interop 디버깅이 사용 되는 경우 연결 된 프로세스에서 콘솔 잠금을 유지 하 고 디버그 이벤트에서 중지할 수 있습니다. 그러면 디버거가 콘솔 사용 시도를 차단 합니다. 이 문제를 방지 하려면 `dwCreationFlags` 매개 변수에서 CREATE_NEW_CONSOLE 플래그를 설정 합니다.  
  
 IA-64 기반 및 AMD64 기반 플랫폼과 같은 Win9x 및 비 x86 플랫폼에서는 Interop 디버깅이 지원 되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
