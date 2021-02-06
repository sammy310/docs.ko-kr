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
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="27a7f-103">ICorDebugRegisterSet::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="27a7f-103">ICorDebugRegisterSet::SetThreadContext Method</span></span>

<span data-ttu-id="27a7f-104">`SetThreadContext` 는 .NET Framework 버전 2.0에 구현 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27a7f-104">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="27a7f-105">이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="27a7f-105">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="27a7f-106">더 높은 수준의 작업 [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) 를 사용 하 여 스레드의 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a7f-106">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a7f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="27a7f-107">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="27a7f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27a7f-108">Requirements</span></span>  

 <span data-ttu-id="27a7f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27a7f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a7f-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27a7f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27a7f-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27a7f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27a7f-112">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="27a7f-112">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a7f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27a7f-113">See also</span></span>

- [<span data-ttu-id="27a7f-114">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27a7f-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="27a7f-115">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27a7f-115">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
