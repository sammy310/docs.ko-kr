---
description: '자세히 알아보기: ICorDebugManagedCallback:: Exception 메서드'
title: ICorDebugManagedCallback::Exception 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: f738c328e1f6edfeb61a1d5e2ba8f9dd827d05dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790973"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="03b08-103">ICorDebugManagedCallback::Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="03b08-103">ICorDebugManagedCallback::Exception Method</span></span>

<span data-ttu-id="03b08-104">관리 코드에서 예외가 throw 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="03b08-104">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b08-105">구문</span><span class="sxs-lookup"><span data-stu-id="03b08-105">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b08-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03b08-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="03b08-107">진행 예외가 throw 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03b08-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="03b08-108">진행 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03b08-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="03b08-109">진행 이 값이 이면 `false` 응용 프로그램에서 예외를 아직 처리 하지 않은 것이 고, 그렇지 않으면 예외가 처리 되지 않고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="03b08-109">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03b08-110">설명</span><span class="sxs-lookup"><span data-stu-id="03b08-110">Remarks</span></span>  

 <span data-ttu-id="03b08-111">특정 예외는 스레드 개체에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03b08-111">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b08-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03b08-112">Requirements</span></span>  

 <span data-ttu-id="03b08-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03b08-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03b08-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03b08-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03b08-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03b08-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03b08-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03b08-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b08-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03b08-117">See also</span></span>

- [<span data-ttu-id="03b08-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03b08-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
