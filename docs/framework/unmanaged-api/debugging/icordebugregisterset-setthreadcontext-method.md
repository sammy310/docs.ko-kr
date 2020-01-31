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
ms.openlocfilehash: dc2a41524d3fafe1cb45c9494d80aabe7dae0ed8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792035"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="94f6d-102">ICorDebugRegisterSet::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="94f6d-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="94f6d-103">`SetThreadContext`는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94f6d-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="94f6d-104">이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="94f6d-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94f6d-105">더 높은 수준의 작업 [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) 를 사용 하 여 스레드의 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f6d-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94f6d-106">구문</span><span class="sxs-lookup"><span data-stu-id="94f6d-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="94f6d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94f6d-107">Requirements</span></span>  
 <span data-ttu-id="94f6d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94f6d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94f6d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94f6d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94f6d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94f6d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94f6d-111">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="94f6d-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94f6d-112">참조</span><span class="sxs-lookup"><span data-stu-id="94f6d-112">See also</span></span>

- [<span data-ttu-id="94f6d-113">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94f6d-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="94f6d-114">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="94f6d-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
