---
title: ICorDebugILFrame2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2
helpviewer_keywords:
- ICorDebugILFrame2 interface [.NET Framework debugging]
ms.assetid: f94b9d53-d8f8-4424-a95e-53a1bfd26e4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4f57f27ec92e7977b46ebfa5967b0590674d2a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113440"
---
# <a name="icordebugilframe2-interface"></a><span data-ttu-id="2623f-102">ICorDebugILFrame2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2623f-102">ICorDebugILFrame2 Interface</span></span>

<span data-ttu-id="2623f-103">ICorDebugILFrame 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2623f-103">A logical extension of the ICorDebugILFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2623f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2623f-104">Methods</span></span>  
  
|<span data-ttu-id="2623f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2623f-105">Method</span></span>|<span data-ttu-id="2623f-106">설명</span><span class="sxs-lookup"><span data-stu-id="2623f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2623f-107">EnumerateTypeParameters 메서드</span><span class="sxs-lookup"><span data-stu-id="2623f-107">EnumerateTypeParameters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md)|<span data-ttu-id="2623f-108">포함 된 ICorDebugTypeEnum 개체를 가져옵니다는 <xref:System.Type> 이 프레임에서 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2623f-108">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>|  
|[<span data-ttu-id="2623f-109">RemapFunction 메서드</span><span class="sxs-lookup"><span data-stu-id="2623f-109">RemapFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-remapfunction-method.md)|<span data-ttu-id="2623f-110">새 MSIL 오프셋을 지정 하 여 편집된 된 함수를 다시 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="2623f-110">Remaps an edited function by specifying the new MSIL offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2623f-111">설명</span><span class="sxs-lookup"><span data-stu-id="2623f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2623f-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2623f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2623f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2623f-113">Requirements</span></span>  
 <span data-ttu-id="2623f-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2623f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2623f-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2623f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2623f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2623f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2623f-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2623f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2623f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2623f-118">See also</span></span>

- [<span data-ttu-id="2623f-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2623f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
