---
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
ms.openlocfilehash: 63ddce2f299133fcfe0da17897eaf0c6a9509a55
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378236"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a>ICorDebugRegisterSet::SetThreadContext 메서드
`SetThreadContext`는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다. 이 메서드를 호출 하지 마십시오.  
  
> [!NOTE]
> 더 높은 수준의 작업 [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) 를 사용 하 여 스레드의 컨텍스트를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
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
