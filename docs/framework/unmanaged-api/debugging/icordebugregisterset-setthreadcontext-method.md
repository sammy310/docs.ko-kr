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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b1ea34c187de99d23b05b5e1a30c53bc54a6c0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197401"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="bb063-102">ICorDebugRegisterSet::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="bb063-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="bb063-103">`SetThreadContext` .NET Framework 버전 2.0에서는 구현 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb063-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="bb063-104">이 메서드를 호출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="bb063-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb063-105">더 높은 수준의 작업 사용 [icordebugnativeframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) 스레드 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb063-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb063-106">구문</span><span class="sxs-lookup"><span data-stu-id="bb063-106">Syntax</span></span>  
  
```  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bb063-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb063-107">Requirements</span></span>  
 <span data-ttu-id="bb063-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb063-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb063-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb063-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb063-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb063-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb063-111">**.NET framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="bb063-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb063-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb063-112">See also</span></span>

- [<span data-ttu-id="bb063-113">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb063-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="bb063-114">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bb063-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
