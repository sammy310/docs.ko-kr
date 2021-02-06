---
description: '자세히 알아보기: ICorDebugRegisterSet:: SetThreadContext 메서드'
title: ICorDebugRegisterSet::SetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 8d874b1864e85e477260632ad6012dbbf10aefb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637692"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>ICorDebugRegisterSet::SetThreadContext 메서드

`SetThreadContext` 는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다. 이 메서드를 호출 하지 마십시오.  
  
> [!NOTE]
> 더 높은 수준의 작업 [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) 를 사용 하 여 스레드의 컨텍스트를 설정 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 1.1, 1.0  
  
## <a name="see-also"></a>참고 항목

- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
