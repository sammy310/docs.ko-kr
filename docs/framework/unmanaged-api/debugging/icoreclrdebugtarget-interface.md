---
title: ICoreClrDebugTarget 인터페이스
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
ms.openlocfilehash: 83afe121b6bf0de3c5542695e38b6605db7a8b6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121825"
---
# <a name="icoreclrdebugtarget-interface"></a>ICoreClrDebugTarget 인터페이스
참조 횟수를 제어 하 고, 프로세스를 열거 하 고, 원격 Macintosh Silverlight 대상에 연결 된 디버거와 연결 된 메모리를 해제 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ICoreClrDebugTarget::EnumProcesses 메서드](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.|  
|[ICoreClrDebugTarget::EnumRuntimes 메서드](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|원격 컴퓨터에서 지정 된 프로세스의 Clr (공용 언어 런타임)을 열거 합니다.|  
|[ICoreClrDebugTarget::FreeMemory 메서드](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|이 클래스의 열거형 메서드에 의해 할당 된 메모리를 해제 합니다.|  
  
## <a name="remarks"></a>주의  
 현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상의 디버깅에만 지원 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참조

- [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
