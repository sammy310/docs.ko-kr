---
title: ICorDebugFunction3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c29d631f84ce2dd7532e32951e71d6597218ebb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088862"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="ac582-102">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac582-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="ac582-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="ac582-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ac582-104">ReJIT 요청의 코드에 대 한 액세스를 제공 하는 ICorDebugFunction 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac582-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac582-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ac582-105">Methods</span></span>  
  
|<span data-ttu-id="ac582-106">메서드</span><span class="sxs-lookup"><span data-stu-id="ac582-106">Method</span></span>|<span data-ttu-id="ac582-107">설명</span><span class="sxs-lookup"><span data-stu-id="ac582-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac582-108">GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="ac582-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="ac582-109">한 인터페이스 포인터를 가져옵니다는 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 활성 ReJIT 요청의 IL을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac582-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac582-110">설명</span><span class="sxs-lookup"><span data-stu-id="ac582-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac582-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac582-111">Requirements</span></span>  
 <span data-ttu-id="ac582-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ac582-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac582-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac582-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac582-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac582-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac582-115">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac582-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac582-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac582-116">See also</span></span>

- [<span data-ttu-id="ac582-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac582-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ac582-118">디버깅</span><span class="sxs-lookup"><span data-stu-id="ac582-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ac582-119">ReJIT: 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="ac582-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
