---
description: '자세히 알아보기: ICorDebugFunction3 인터페이스'
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
ms.openlocfilehash: f6f3ce78fbb0ca7efb6ba6a95da20f8c698b923c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692071"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="b2f61-103">ICorDebugFunction3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2f61-103">ICorDebugFunction3 Interface</span></span>

<span data-ttu-id="b2f61-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="b2f61-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b2f61-105">ReJIT 요청의 코드에 액세스할 수 있도록 ICorDebugFunction 인터페이스를 논리적으로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f61-105">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2f61-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b2f61-106">Methods</span></span>  
  
|<span data-ttu-id="b2f61-107">메서드</span><span class="sxs-lookup"><span data-stu-id="b2f61-107">Method</span></span>|<span data-ttu-id="b2f61-108">설명</span><span class="sxs-lookup"><span data-stu-id="b2f61-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2f61-109">GetActiveReJitRequestILCode 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f61-109">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="b2f61-110">활성 ReJIT 요청에서 IL을 포함 하는 [ICorDebugILCode](icordebugilcode-interface.md) 에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2f61-110">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2f61-111">설명</span><span class="sxs-lookup"><span data-stu-id="b2f61-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2f61-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2f61-112">Requirements</span></span>  

 <span data-ttu-id="b2f61-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f61-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2f61-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2f61-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2f61-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2f61-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2f61-116">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2f61-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f61-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2f61-117">See also</span></span>

- [<span data-ttu-id="b2f61-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2f61-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b2f61-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="b2f61-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="b2f61-120">ReJIT: How-To 가이드</span><span class="sxs-lookup"><span data-stu-id="b2f61-120">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
