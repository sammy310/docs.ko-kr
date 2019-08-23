---
title: ICorDebugObjectEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1faa78150659b4397cd4174583b607e1f7841b8f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943354"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="3db2a-102">ICorDebugObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db2a-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="3db2a-103">ICorDebugEnum 메서드를 구현 하 고 개체의 배열을 Rva (상대 가상 주소)로 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3db2a-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3db2a-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3db2a-104">Methods</span></span>  
  
|<span data-ttu-id="3db2a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3db2a-105">Method</span></span>|<span data-ttu-id="3db2a-106">Description</span><span class="sxs-lookup"><span data-stu-id="3db2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3db2a-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="3db2a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="3db2a-108">현재 위치에서 시작 하 여 열거형에서 지정 된 개체 수의 Rva를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3db2a-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3db2a-109">설명</span><span class="sxs-lookup"><span data-stu-id="3db2a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3db2a-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3db2a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3db2a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3db2a-111">Requirements</span></span>  
 <span data-ttu-id="3db2a-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3db2a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db2a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3db2a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3db2a-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3db2a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3db2a-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3db2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db2a-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="3db2a-116">See also</span></span>

- [<span data-ttu-id="3db2a-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3db2a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
