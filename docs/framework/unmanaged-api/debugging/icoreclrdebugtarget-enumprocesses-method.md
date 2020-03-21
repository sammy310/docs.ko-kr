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
ms.openlocfilehash: 6484832e8e737b9a0d0b3eaf3ede4078729f7a4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178433"
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
 【아웃】 원격 컴퓨터에서 실행되는 프로세스를 나타내는 [CoreClrDebugPropro](coreclrdebugprocinfo-structure.md) 정보 구조의 배열입니다.  
  
## <a name="return-value"></a>Return Value  
 S_OK  
 성공했습니다.  
  
 E_OUTOFMEMORY  
 `ppProcs`에 대해 충분한 메모리를 할당할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 기타 실패  
  
## <a name="remarks"></a>설명  
 이 메서드에서 할당된 메모리를 해제하려면 [ICoreClrDebugTarget::FreeMemory](icoreclrdebugtarget-freememory-method.md) 메서드를 호출합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코어클러원격디버깅인터페이스.h  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET 프레임워크 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목

- [ICoreClrDebugTarget 인터페이스](icoreclrdebugtarget-interface.md)
