---
title: ICorDebugAppDomainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48c222a34e2e78f29c33e49da331d97d409bae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949756"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="76ff5-102">ICorDebugAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76ff5-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="76ff5-103">열거형의 다음 위치에서 시작 하 여 지정 된 `ICorDebugAppDomainEnum` 수의 값을 반환 하는 메서드를제공합니다.`Next`</span><span class="sxs-lookup"><span data-stu-id="76ff5-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="76ff5-104">이 인터페이스는 "ICorDebugEnum"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="76ff5-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="76ff5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="76ff5-105">Methods</span></span>  
  
|<span data-ttu-id="76ff5-106">메서드</span><span class="sxs-lookup"><span data-stu-id="76ff5-106">Method</span></span>|<span data-ttu-id="76ff5-107">설명</span><span class="sxs-lookup"><span data-stu-id="76ff5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="76ff5-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="76ff5-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="76ff5-109">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76ff5-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ff5-110">설명</span><span class="sxs-lookup"><span data-stu-id="76ff5-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="76ff5-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76ff5-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ff5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76ff5-112">Requirements</span></span>  
 <span data-ttu-id="76ff5-113">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="76ff5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ff5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76ff5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76ff5-115">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76ff5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76ff5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ff5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ff5-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="76ff5-117">See also</span></span>

- [<span data-ttu-id="76ff5-118">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76ff5-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="76ff5-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76ff5-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
