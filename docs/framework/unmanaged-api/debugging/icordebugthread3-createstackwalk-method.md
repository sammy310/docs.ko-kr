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
ms.openlocfilehash: 64f6bc9abb8105cdfa942c2aaca71994e8a91765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791410"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="8ebdb-102">ICorDebugThread3::CreateStackWalk 메서드</span><span class="sxs-lookup"><span data-stu-id="8ebdb-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="8ebdb-103">스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebdb-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ebdb-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ebdb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ebdb-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="8ebdb-106">제한이 스택을 해제 하려는 스레드에 대 한 [ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ebdb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8ebdb-107">Return Value</span></span>  
 <span data-ttu-id="8ebdb-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8ebdb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ebdb-109">HRESULT</span></span>|<span data-ttu-id="8ebdb-110">설명</span><span class="sxs-lookup"><span data-stu-id="8ebdb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ebdb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ebdb-111">S_OK</span></span>|<span data-ttu-id="8ebdb-112">`ICorDebugStackWalk` 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="8ebdb-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ebdb-113">E_FAIL</span></span>|<span data-ttu-id="8ebdb-114">`ICorDebugStackWalk` 개체를 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="8ebdb-115">예외</span><span class="sxs-lookup"><span data-stu-id="8ebdb-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ebdb-116">주의</span><span class="sxs-lookup"><span data-stu-id="8ebdb-116">Remarks</span></span>  
 <span data-ttu-id="8ebdb-117">`CreateStackWalk` 메서드가 성공 하면 반환 된 `ICorDebugStackWalk` 개체의 컨텍스트가 스레드의 현재 컨텍스트로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ebdb-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ebdb-118">Requirements</span></span>  
 <span data-ttu-id="8ebdb-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ebdb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ebdb-120">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ebdb-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ebdb-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ebdb-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ebdb-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ebdb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebdb-123">참조</span><span class="sxs-lookup"><span data-stu-id="8ebdb-123">See also</span></span>

- [<span data-ttu-id="8ebdb-124">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ebdb-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8ebdb-125">디버깅</span><span class="sxs-lookup"><span data-stu-id="8ebdb-125">Debugging</span></span>](index.md)
