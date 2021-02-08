---
description: '자세히 알아보기: ICorDebugManagedCallback:: ControlCTrap 메서드'
title: ICorDebugManagedCallback::ControlCTrap 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: 9fa71dacb20ff6df21d8aabb687c2601f27643c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791070"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="0bfe9-103">ICorDebugManagedCallback::ControlCTrap 메서드</span><span class="sxs-lookup"><span data-stu-id="0bfe9-103">ICorDebugManagedCallback::ControlCTrap Method</span></span>

<span data-ttu-id="0bfe9-104">디버깅 중인 프로세스에서 CTRL + C가 트랩 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe9-104">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bfe9-105">구문</span><span class="sxs-lookup"><span data-stu-id="0bfe9-105">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bfe9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bfe9-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="0bfe9-107">진행 CTRL + C가 트래핑 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe9-107">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bfe9-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="0bfe9-108">Return Value</span></span>  
  
|<span data-ttu-id="0bfe9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bfe9-109">HRESULT</span></span>|<span data-ttu-id="0bfe9-110">설명</span><span class="sxs-lookup"><span data-stu-id="0bfe9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bfe9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bfe9-111">S_OK</span></span>|<span data-ttu-id="0bfe9-112">디버거는 CTRL + C 트랩을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe9-112">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="0bfe9-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0bfe9-113">S_FALSE</span></span>|<span data-ttu-id="0bfe9-114">디버거는 CTRL + C 트랩을 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe9-114">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bfe9-115">설명</span><span class="sxs-lookup"><span data-stu-id="0bfe9-115">Remarks</span></span>  

 <span data-ttu-id="0bfe9-116">이 콜백에 대해 프로세스 내의 모든 응용 프로그램 도메인이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bfe9-116">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bfe9-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bfe9-117">Requirements</span></span>  

 <span data-ttu-id="0bfe9-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0bfe9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bfe9-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bfe9-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bfe9-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bfe9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bfe9-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bfe9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bfe9-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bfe9-122">See also</span></span>

- [<span data-ttu-id="0bfe9-123">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bfe9-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
