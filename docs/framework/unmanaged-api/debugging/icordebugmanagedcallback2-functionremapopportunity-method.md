---
title: ICorDebugManagedCallback2::FunctionRemapOpportunity 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.FunctionRemapOpportunity
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::FunctionRemapOpportunity
helpviewer_keywords:
- FunctionRemapOpportunity method [.NET Framework debugging]
- ICorDebugManagedCallback2::FunctionRemapOpportunity method [.NET Framework debugging]
ms.assetid: 0d6471bc-ad9b-4b1d-a307-c10443918863
topic_type:
- apiref
ms.openlocfilehash: bc6543b46200dd611e13bdf55aabfabd8302e70a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793343"
---
# <a name="icordebugmanagedcallback2functionremapopportunity-method"></a><span data-ttu-id="08561-102">ICorDebugManagedCallback2::FunctionRemapOpportunity 메서드</span><span class="sxs-lookup"><span data-stu-id="08561-102">ICorDebugManagedCallback2::FunctionRemapOpportunity Method</span></span>
<span data-ttu-id="08561-103">코드 실행이 이전 버전의 편집 된 함수에서 시퀀스 위치에 도달 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="08561-103">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08561-104">구문</span><span class="sxs-lookup"><span data-stu-id="08561-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionRemapOpportunity (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFunction    *pOldFunction,  
    [in] ICorDebugFunction    *pNewFunction,  
    [in] ULONG32              oldILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08561-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08561-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="08561-106">진행 편집 된 함수를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08561-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the edited function.</span></span>  
  
 `pThread`  
 <span data-ttu-id="08561-107">진행 다시 매핑 중단점이 발생 한 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08561-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the remap breakpoint was encountered.</span></span>  
  
 `pOldFunction`  
 <span data-ttu-id="08561-108">진행 스레드에서 현재 실행 중인 함수의 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08561-108">[in] A pointer to an ICorDebugFunction object that represents the version of the function that is currently running on the thread.</span></span>  
  
 `pNewFunction`  
 <span data-ttu-id="08561-109">진행 함수의 최신 버전을 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08561-109">[in] A pointer to an ICorDebugFunction object that represents the latest version of the function.</span></span>  
  
 `oldILOffset`  
 <span data-ttu-id="08561-110">진행 이전 버전의 함수에 있는 명령 포인터의 MSIL (Microsoft 중간 언어) 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="08561-110">[in] The Microsoft intermediate language (MSIL) offset of the instruction pointer in the old version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08561-111">주의</span><span class="sxs-lookup"><span data-stu-id="08561-111">Remarks</span></span>  
 <span data-ttu-id="08561-112">이 콜백은 디버거가 [ICorDebugILFrame2:: RemapFunction](icordebugilframe2-remapfunction-method.md) 메서드를 호출 하 여 지정 된 함수의 새 버전에서 적절 한 위치에 명령 포인터를 다시 매핑할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="08561-112">This callback gives the debugger an opportunity to remap the instruction pointer to its proper place in the new version of the specified function by calling the [ICorDebugILFrame2::RemapFunction](icordebugilframe2-remapfunction-method.md) method.</span></span> <span data-ttu-id="08561-113">[ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 메서드를 호출 하기 전에 디버거가 `RemapFunction`를 호출 하지 않으면 런타임은 계속 이전 코드를 실행 하 고 다음 시퀀스 위치에서 다른 `FunctionRemapOpportunity` 콜백을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08561-113">If the debugger does not call `RemapFunction` before calling the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method, the runtime will continue to execute the old code and will fire another `FunctionRemapOpportunity` callback at the next sequence point.</span></span>  
  
 <span data-ttu-id="08561-114">이 콜백은 디버거가 S_OK 반환 될 때까지 지정 된 함수의 이전 버전을 실행 하는 모든 프레임에 대해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08561-114">This callback will be invoked for every frame that is executing an older version of the given function until the debugger returns S_OK.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08561-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08561-115">Requirements</span></span>  
 <span data-ttu-id="08561-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08561-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08561-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08561-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08561-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08561-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08561-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08561-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08561-120">참조</span><span class="sxs-lookup"><span data-stu-id="08561-120">See also</span></span>

- [<span data-ttu-id="08561-121">ICorDebugManagedCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08561-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="08561-122">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08561-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
