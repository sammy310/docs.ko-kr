---
description: '자세히 알아보기: ICoreClrDebugTarget:: FreeMemory 메서드'
title: ICoreClrDebugTarget::FreeMemory 메서드
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: 9572e0c3df1fdd064e78ba170d39c1415c68dc85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690004"
---
# <a name="icoreclrdebugtargetfreememory-method"></a>ICoreClrDebugTarget::FreeMemory 메서드

[ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumprocesses-method.md) 및 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumruntimes-method.md) 메서드에 의해 할당 된 메모리를 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pMemory`  
 진행 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumprocesses-method.md) 또는 [ICoreClrDebugTarget:: enumprocesses](icoreclrdebugtarget-enumruntimes-method.md) 메서드에 의해 반환 된 배열에 대 한 포인터입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CoreClrRemoteDebuggingInterfaces  
  
 **라이브러리:** mscordbi_macx86.dll  
  
 **.NET Framework 버전:** 3.5 SP1  
  
## <a name="see-also"></a>참고 항목

- [ICoreClrDebugTarget 인터페이스](icoreclrdebugtarget-interface.md)
