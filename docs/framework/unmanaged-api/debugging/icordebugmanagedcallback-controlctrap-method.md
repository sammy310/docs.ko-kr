---
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
ms.openlocfilehash: 63f7bf8c09480b9ce2cfb8eb8dc66e4a6133ef8f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777481"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="7f311-102">ICorDebugManagedCallback::ControlCTrap 메서드</span><span class="sxs-lookup"><span data-stu-id="7f311-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="7f311-103">디버깅 중인 프로세스에서 CTRL + C가 트랩 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7f311-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f311-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f311-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f311-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f311-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7f311-106">진행 CTRL + C가 트래핑 된 프로세스를 나타내는 ICorDebugProcess 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7f311-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f311-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7f311-107">Return Value</span></span>  
  
|<span data-ttu-id="7f311-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f311-108">HRESULT</span></span>|<span data-ttu-id="7f311-109">설명</span><span class="sxs-lookup"><span data-stu-id="7f311-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f311-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f311-110">S_OK</span></span>|<span data-ttu-id="7f311-111">디버거는 CTRL + C 트랩을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f311-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="7f311-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7f311-112">S_FALSE</span></span>|<span data-ttu-id="7f311-113">디버거는 CTRL + C 트랩을 처리 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f311-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f311-114">주의</span><span class="sxs-lookup"><span data-stu-id="7f311-114">Remarks</span></span>  
 <span data-ttu-id="7f311-115">이 콜백에 대해 프로세스 내의 모든 응용 프로그램 도메인이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f311-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f311-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f311-116">Requirements</span></span>  
 <span data-ttu-id="7f311-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f311-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f311-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f311-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f311-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f311-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f311-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f311-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f311-121">참조</span><span class="sxs-lookup"><span data-stu-id="7f311-121">See also</span></span>

- [<span data-ttu-id="7f311-122">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f311-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
