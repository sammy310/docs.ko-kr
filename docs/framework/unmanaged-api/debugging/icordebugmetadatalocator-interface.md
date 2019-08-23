---
title: ICorDebugMetaDataLocator 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cf11ec294486fdc14d424e731eac8e4745d892
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939861"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="9ca66-102">ICorDebugMetaDataLocator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ca66-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="9ca66-103">디버거에 메타데이터 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca66-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ca66-104">메서드</span><span class="sxs-lookup"><span data-stu-id="9ca66-104">Methods</span></span>  
  
|<span data-ttu-id="9ca66-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9ca66-105">Method</span></span>|<span data-ttu-id="9ca66-106">설명</span><span class="sxs-lookup"><span data-stu-id="9ca66-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ca66-107">GetMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="9ca66-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="9ca66-108">디버거가 요청한 작업을 완료하는 데 필요한 메타데이터가 포함된 모듈의 전체 경로를 반환하도록 디버거에 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca66-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ca66-109">설명</span><span class="sxs-lookup"><span data-stu-id="9ca66-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ca66-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca66-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ca66-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ca66-111">Requirements</span></span>  
 <span data-ttu-id="9ca66-112">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ca66-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ca66-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ca66-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ca66-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ca66-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ca66-115">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ca66-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca66-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ca66-116">See also</span></span>

- [<span data-ttu-id="9ca66-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ca66-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9ca66-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="9ca66-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
