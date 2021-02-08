---
description: '자세히 알아보기: ICorDebugThread4:: HadUnhandledException 메서드'
title: ICorDebugThread4::HadUnhandledException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: cd0ccdbdd68c37b5fbdbd705da7136e5d36baa60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800931"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="16e25-103">ICorDebugThread4::HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="16e25-103">ICorDebugThread4::HadUnhandledException Method</span></span>

<span data-ttu-id="16e25-104">스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-104">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e25-105">구문</span><span class="sxs-lookup"><span data-stu-id="16e25-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="16e25-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16e25-106">Parameters</span></span>  

 `ppBlockingObjectEnum`  
 <span data-ttu-id="16e25-107">제한이 [CorDebugBlockingObject](cordebugblockingobject-structure.md) 구조체의 정렬 된 열거 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-107">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16e25-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="16e25-108">Return Value</span></span>  

 <span data-ttu-id="16e25-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="16e25-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16e25-110">HRESULT</span></span>|<span data-ttu-id="16e25-111">설명</span><span class="sxs-lookup"><span data-stu-id="16e25-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16e25-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="16e25-112">S_OK</span></span>|<span data-ttu-id="16e25-113">스레드의 생성 후에 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-113">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="16e25-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="16e25-114">S_FALSE</span></span>|<span data-ttu-id="16e25-115">스레드에 처리 되지 않은 예외가 발생 한 적이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-115">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16e25-116">설명</span><span class="sxs-lookup"><span data-stu-id="16e25-116">Remarks</span></span>  

 <span data-ttu-id="16e25-117">이 메서드는 스레드에 처리 되지 않은 예외가 발생 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-117">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="16e25-118">처리 되지 않은 예외 콜백이 트리거하거나 네이티브 JIT 연결이 시작 될 때이 메서드는 S_OK 반환 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-118">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="16e25-119">[ICorDebugThread 예외](icordebugthread-getcurrentexception-method.md) 메서드에서 처리 되지 않은 예외를 반환 한다는 보장이 없습니다. 그러나 처리 되지 않은 예외 콜백을 가져온 후 또는 네이티브 JIT 연결에 프로세스를 아직 계속 하지 않은 경우에는이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-119">There is no guarantee that the [ICorDebugThread.GetCurrentException](icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="16e25-120">또한 네이티브 JIT 연결이 트리거되는 동안 처리 되지 않은 예외가 있는 스레드가 둘 이상 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-120">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="16e25-121">이러한 경우 JIT 연결을 트리거한 예외를 확인할 수 있는 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16e25-121">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16e25-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16e25-122">Requirements</span></span>  

 <span data-ttu-id="16e25-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16e25-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e25-124">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16e25-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16e25-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16e25-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16e25-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e25-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e25-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16e25-127">See also</span></span>

- [<span data-ttu-id="16e25-128">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16e25-128">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="16e25-129">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16e25-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="16e25-130">디버깅</span><span class="sxs-lookup"><span data-stu-id="16e25-130">Debugging</span></span>](index.md)
