---
title: ICorDebugManagedCallback::CreateThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ca11853100228287c4148a2330cbc5a4609550f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472511"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="bf2f1-102">ICorDebugManagedCallback::CreateThread 메서드</span><span class="sxs-lookup"><span data-stu-id="bf2f1-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="bf2f1-103">스레드가 관리 코드 실행 시작 되도록 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf2f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="bf2f1-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf2f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf2f1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bf2f1-106">[in] 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="bf2f1-107">[in] 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf2f1-108">설명</span><span class="sxs-lookup"><span data-stu-id="bf2f1-108">Remarks</span></span>  
 <span data-ttu-id="bf2f1-109">스레드는 실행할 첫 번째 관리 되는 코드 명령에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf2f1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf2f1-110">Requirements</span></span>  
 <span data-ttu-id="bf2f1-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf2f1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf2f1-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf2f1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf2f1-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf2f1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf2f1-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf2f1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf2f1-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bf2f1-115">See also</span></span>
- [<span data-ttu-id="bf2f1-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf2f1-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
