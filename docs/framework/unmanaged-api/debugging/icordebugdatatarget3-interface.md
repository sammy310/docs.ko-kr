---
title: ICorDebugDataTarget3 인터페이스
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: 04e7b9a064d4a06a06b8a1518f06092ba79a3561
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783495"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="5a287-102">ICorDebugDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a287-102">ICorDebugDataTarget3 Interface</span></span>
<span data-ttu-id="5a287-103">[ICorDebugDataTarget](icordebugdatatarget-interface.md) 인터페이스를 논리적으로 확장 하 여 로드 된 모듈에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a287-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="5a287-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5a287-104">Method</span></span>  
  
|<span data-ttu-id="5a287-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5a287-105">Method</span></span>|<span data-ttu-id="5a287-106">설명</span><span class="sxs-lookup"><span data-stu-id="5a287-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a287-107">GetLoadedModules 메서드</span><span class="sxs-lookup"><span data-stu-id="5a287-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="5a287-108">지금까지 로드된 모듈 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a287-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a287-109">주의</span><span class="sxs-lookup"><span data-stu-id="5a287-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a287-110">이 인터페이스는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a287-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5a287-111">.NET 네이티브 외부의 ICorDebug 시나리오에 대해 이 인터페이스를 구현하는 경우 공용 언어 런타임에서 이 인터페이스를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5a287-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a287-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a287-112">Requirements</span></span>  
 <span data-ttu-id="5a287-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a287-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a287-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a287-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a287-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a287-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a287-116">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a287-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a287-117">참조</span><span class="sxs-lookup"><span data-stu-id="5a287-117">See also</span></span>

- [<span data-ttu-id="5a287-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a287-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5a287-119">디버깅</span><span class="sxs-lookup"><span data-stu-id="5a287-119">Debugging</span></span>](index.md)
