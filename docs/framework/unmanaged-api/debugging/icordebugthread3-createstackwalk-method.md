---
title: ICorDebugThread3::CreateStackWalk 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7969d8482970b13951938203262f6ce8f9bf574a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229305"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="c5271-102">ICorDebugThread3::CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="c5271-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="c5271-103">만듭니다는 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 해제 하려는 해당 스택 스레드에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c5271-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5271-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5271-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5271-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5271-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="c5271-106">[out] 주소에 대 한 포인터를 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 해제 하려는 해당 스택 스레드에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c5271-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5271-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c5271-107">Return Value</span></span>  
 <span data-ttu-id="c5271-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5271-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c5271-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5271-109">HRESULT</span></span>|<span data-ttu-id="c5271-110">설명</span><span class="sxs-lookup"><span data-stu-id="c5271-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5271-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5271-111">S_OK</span></span>|<span data-ttu-id="c5271-112">`ICorDebugStackWalk` 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="c5271-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="c5271-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5271-113">E_FAIL</span></span>|<span data-ttu-id="c5271-114">`ICorDebugStackWalk` 개체가 생성 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c5271-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c5271-115">예외</span><span class="sxs-lookup"><span data-stu-id="c5271-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5271-116">설명</span><span class="sxs-lookup"><span data-stu-id="c5271-116">Remarks</span></span>  
 <span data-ttu-id="c5271-117">경우는 `CreateStackWalk` 메서드가 성공 하면 반환 된 `ICorDebugStackWalk` 개체의 컨텍스트에 스레드의 현재 컨텍스트로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5271-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5271-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5271-118">Requirements</span></span>  
 <span data-ttu-id="c5271-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c5271-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5271-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5271-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5271-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5271-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5271-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5271-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5271-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5271-123">See also</span></span>

- [<span data-ttu-id="c5271-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5271-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c5271-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="c5271-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
