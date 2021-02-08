---
description: '자세히 알아보기: ICoreClrDebugTarget:: EnumRuntimes 메서드'
title: ICoreClrDebugTarget::EnumRuntimes 메서드
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
ms.openlocfilehash: 675747106b2acec2e8be3fcdf15831958bea7c7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794626"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>ICoreClrDebugTarget::EnumRuntimes 메서드

원격 컴퓨터에서 실행 중인 지정된 프로세스의 CLR(공용 언어 런타임)을 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a>매개 변수  

 `dwInternalProcessID`  
 [in] 런타임을 열거하려는 프로세스의 내부 프로세스 ID입니다. 이는 `m_dwInternalID` 해당 [CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)에서 가져온 것입니다.  
  
 `pcRuntimes`  
 [out] `ppRuntimes`에 반환된 런타임 수입니다. 이 값은 0일 수 있습니다.  
  
 `ppRuntimes`  
 제한이 원격 대상 프로세스에 로드 된 런타임을 나타내는 [CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md) 구조체의 배열입니다.  
  
## <a name="return-value"></a>Return Value  

 S_OK  
 성공했습니다.  
  
 S_FALSE  
 `dwInternalProcessID`가 컴퓨터에서 실행 중인 프로세스와 일치하지 않습니다. 프로세스가 종료된 것 같습니다. `pcRuntimes` 및 `ppRuntimes`가 null이 됩니다.  
  
 E_OUTOFMEMORY  
 `ppRuntimes`에 대해 충분한 메모리를 할당할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 기타 실패  
  
## <a name="remarks"></a>설명  

 이 메서드에 의해 할당 된 메모리를 해제 하려면 [ICoreClrDebugTarget:: FreeMemory](icoreclrdebugtarget-freememory-method.md) 메서드를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목

- [ICoreClrDebugTarget 인터페이스](icoreclrdebugtarget-interface.md)
