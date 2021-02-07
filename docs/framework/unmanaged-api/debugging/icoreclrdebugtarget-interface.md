---
description: '자세히 알아보기: ICoreClrDebugTarget 인터페이스'
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
ms.openlocfilehash: f0ed4dd75cd1daca6e83617433b29bbaecb1dd36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728758"
---
# <a name="icoreclrdebugtarget-interface"></a>ICoreClrDebugTarget 인터페이스

참조 횟수를 제어 하 고, 프로세스를 열거 하 고, 원격 Macintosh Silverlight 대상에 연결 된 디버거와 연결 된 메모리를 해제 하는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>Syntax  
  
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
|[ICoreClrDebugTarget::EnumProcesses 메서드](icoreclrdebugtarget-enumprocesses-method.md)|원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.|  
|[ICoreClrDebugTarget::EnumRuntimes 메서드](icoreclrdebugtarget-enumruntimes-method.md)|원격 컴퓨터에서 지정 된 프로세스의 Clr (공용 언어 런타임)을 열거 합니다.|  
|[ICoreClrDebugTarget::FreeMemory 메서드](icoreclrdebugtarget-freememory-method.md)|이 클래스의 열거형 메서드에 의해 할당 된 메모리를 해제 합니다.|  
  
## <a name="remarks"></a>설명  

 현재이 기능은 원격 Macintosh 컴퓨터에서 실행 되는 Silverlight 기반 응용 프로그램 대상의 디버깅에만 지원 됩니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRemoteTarget 인터페이스](icordebugremotetarget-interface.md)
- [ICorDebug 인터페이스](icordebug-interface.md)

- [디버깅 인터페이스](debugging-interfaces.md)
