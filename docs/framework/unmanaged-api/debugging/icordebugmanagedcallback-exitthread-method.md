---
title: ICorDebugManagedCallback::ExitThread 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
ms.openlocfilehash: 2ccb06b974cb17dff987ba42b647224cdc4c4ff2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688939"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="29714-102">ICorDebugManagedCallback::ExitThread 메서드</span><span class="sxs-lookup"><span data-stu-id="29714-102">ICorDebugManagedCallback::ExitThread Method</span></span>

<span data-ttu-id="29714-103">관리 코드를 실행 하는 스레드가 종료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="29714-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29714-104">구문</span><span class="sxs-lookup"><span data-stu-id="29714-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29714-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="29714-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="29714-106">진행 관리 되는 스레드가 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="29714-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="29714-107">진행 관리 되는 스레드를 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="29714-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29714-108">설명</span><span class="sxs-lookup"><span data-stu-id="29714-108">Remarks</span></span>  

 <span data-ttu-id="29714-109">`ExitThread`콜백이 발생 하면 스레드 열거에 스레드가 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29714-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29714-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="29714-110">Requirements</span></span>  

 <span data-ttu-id="29714-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29714-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29714-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29714-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29714-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29714-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29714-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29714-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29714-115">참조</span><span class="sxs-lookup"><span data-stu-id="29714-115">See also</span></span>

- [<span data-ttu-id="29714-116">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="29714-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
