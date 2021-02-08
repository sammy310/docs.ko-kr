---
description: '자세히 알아보기: ICorDebugManagedCallback:: CreateThread 메서드'
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
ms.openlocfilehash: 20d5ce9da34e7082502252eeece2ab34b1f2e902
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791034"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="6b4f5-103">ICorDebugManagedCallback::CreateThread 메서드</span><span class="sxs-lookup"><span data-stu-id="6b4f5-103">ICorDebugManagedCallback::CreateThread Method</span></span>

<span data-ttu-id="6b4f5-104">스레드가 관리 코드 실행을 시작 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="6b4f5-104">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="6b4f5-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b4f5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b4f5-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="6b4f5-107">진행 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4f5-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="6b4f5-108">진행 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b4f5-108">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b4f5-109">설명</span><span class="sxs-lookup"><span data-stu-id="6b4f5-109">Remarks</span></span>  

 <span data-ttu-id="6b4f5-110">스레드는 실행할 첫 번째 관리 되는 코드 명령에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b4f5-110">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b4f5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b4f5-111">Requirements</span></span>  

 <span data-ttu-id="6b4f5-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b4f5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b4f5-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b4f5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b4f5-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b4f5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b4f5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b4f5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b4f5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b4f5-116">See also</span></span>

- [<span data-ttu-id="6b4f5-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b4f5-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
