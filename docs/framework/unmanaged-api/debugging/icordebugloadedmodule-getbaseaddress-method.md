---
title: ICorDebugLoadedModule::GetBaseAddress 메서드
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31b398080c1355441a35871d0685283783efcd52
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501229"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="ebc80-102">ICorDebugLoadedModule::GetBaseAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="ebc80-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="ebc80-103">로드된 모듈의 기본 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ebc80-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebc80-104">구문</span><span class="sxs-lookup"><span data-stu-id="ebc80-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebc80-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebc80-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="ebc80-106">[out] 로드된 모듈의 기본 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ebc80-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebc80-107">설명</span><span class="sxs-lookup"><span data-stu-id="ebc80-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebc80-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebc80-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebc80-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebc80-109">Requirements</span></span>  
 <span data-ttu-id="ebc80-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebc80-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebc80-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebc80-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebc80-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebc80-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebc80-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebc80-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc80-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ebc80-114">See also</span></span>
- [<span data-ttu-id="ebc80-115">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebc80-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="ebc80-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebc80-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
