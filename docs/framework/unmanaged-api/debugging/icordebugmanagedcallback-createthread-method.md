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
ms.openlocfilehash: 5fa3bafd35912a7729833896f7e6f0bb2ff9b121
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212388"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="02ee8-102">ICorDebugManagedCallback::CreateThread 메서드</span><span class="sxs-lookup"><span data-stu-id="02ee8-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="02ee8-103">스레드가 관리 코드 실행을 시작 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="02ee8-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02ee8-104">구문</span><span class="sxs-lookup"><span data-stu-id="02ee8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02ee8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02ee8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="02ee8-106">진행 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02ee8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="02ee8-107">진행 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02ee8-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02ee8-108">설명</span><span class="sxs-lookup"><span data-stu-id="02ee8-108">Remarks</span></span>  
 <span data-ttu-id="02ee8-109">스레드는 실행할 첫 번째 관리 되는 코드 명령에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ee8-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02ee8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02ee8-110">Requirements</span></span>  
 <span data-ttu-id="02ee8-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02ee8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ee8-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02ee8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02ee8-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02ee8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02ee8-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ee8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ee8-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02ee8-115">See also</span></span>

- [<span data-ttu-id="02ee8-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="02ee8-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
