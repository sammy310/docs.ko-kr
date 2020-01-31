---
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
ms.openlocfilehash: 328c10c1895f65b43dc365b1be6b4ec5ef01e720
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777356"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="246d7-102">ICorDebugManagedCallback::Exception 메서드</span><span class="sxs-lookup"><span data-stu-id="246d7-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="246d7-103">관리 코드에서 예외가 throw 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="246d7-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246d7-104">구문</span><span class="sxs-lookup"><span data-stu-id="246d7-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="246d7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="246d7-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="246d7-106">진행 예외가 throw 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="246d7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="246d7-107">진행 예외가 throw 된 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="246d7-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="246d7-108">진행 이 값이 `false`되 면 응용 프로그램에서 예외를 아직 처리 하지 않은 것입니다. 그렇지 않으면 예외가 처리 되지 않고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="246d7-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="246d7-109">주의</span><span class="sxs-lookup"><span data-stu-id="246d7-109">Remarks</span></span>  
 <span data-ttu-id="246d7-110">특정 예외는 스레드 개체에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="246d7-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="246d7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="246d7-111">Requirements</span></span>  
 <span data-ttu-id="246d7-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="246d7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="246d7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="246d7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="246d7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="246d7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="246d7-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="246d7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246d7-116">참조</span><span class="sxs-lookup"><span data-stu-id="246d7-116">See also</span></span>

- [<span data-ttu-id="246d7-117">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="246d7-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
