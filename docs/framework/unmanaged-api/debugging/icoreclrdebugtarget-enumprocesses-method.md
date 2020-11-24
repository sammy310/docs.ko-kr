---
title: ICoreClrDebugTarget::EnumProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 7e0219ae0d7d474812865f01e4e2fcfe2e4da991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679366"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a>ICoreClrDebugTarget::EnumProcesses 메서드

원격 컴퓨터에서 실행 중인 프로세스를 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pcProcs`  
 [out] `ppProcs`에 반환된 프로세스 수입니다. 이 값은 0일 수 있습니다.  
  
 `ppProcs`  
 제한이 원격 컴퓨터에서 실행 중인 프로세스를 나타내는 [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md) 구조체의 배열입니다.  
  
## <a name="return-value"></a>반환 값  

 S_OK  
 성공했습니다.  
  
 E_OUTOFMEMORY  
 `ppProcs`에 대해 충분한 메모리를 할당할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 기타 실패  
  
## <a name="remarks"></a>설명  

 이 메서드에 의해 할당 된 메모리를 해제 하려면 [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) 메서드를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참조

- [ICoreClrDebugTarget 인터페이스](icoreclrdebugtarget-interface.md)
