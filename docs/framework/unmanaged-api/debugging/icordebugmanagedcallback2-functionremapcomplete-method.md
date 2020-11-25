---
title: ICorDebugManagedCallback2::FunctionRemapComplete 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapComplete
helpviewer_keywords:
- FunctionRemapComplete method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapComplete method [.NET Framework debugging]
ms.assetid: 5396c4c3-4ec3-4e3a-a38d-d65b21f0a2fc
topic_type:
- apiref
ms.openlocfilehash: 7eb7fb55a5077d2914eb85a67ca62163a1aa8cc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704606"
---
# <a name="icordebugmanagedcallback2functionremapcomplete-method"></a><span data-ttu-id="5ee6b-102">ICorDebugManagedCallback2::FunctionRemapComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="5ee6b-102">ICorDebugManagedCallback2::FunctionRemapComplete Method</span></span>

<span data-ttu-id="5ee6b-103">코드 실행이 편집 된 함수의 새 버전으로 전환 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5ee6b-103">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ee6b-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapComplete (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee6b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ee6b-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="5ee6b-106">진행 편집 된 함수를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee6b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5ee6b-107">진행 다시 매핑 중단점이 발생 한 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee6b-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pFunction`  
 <span data-ttu-id="5ee6b-108">진행 스레드에서 현재 실행 중인 함수의 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee6b-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function currently running on the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee6b-109">설명</span><span class="sxs-lookup"><span data-stu-id="5ee6b-109">Remarks</span></span>  

 <span data-ttu-id="5ee6b-110">이 콜백은 디버거가 이전에 있던 모든 steppers를 다시 만들 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee6b-110">This callback gives the debugger an opportunity to recreate any steppers that previously existed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee6b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ee6b-111">Requirements</span></span>  

 <span data-ttu-id="5ee6b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee6b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee6b-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ee6b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ee6b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee6b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee6b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee6b-116">참조</span><span class="sxs-lookup"><span data-stu-id="5ee6b-116">See also</span></span>

- [<span data-ttu-id="5ee6b-117">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ee6b-117">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5ee6b-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ee6b-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
