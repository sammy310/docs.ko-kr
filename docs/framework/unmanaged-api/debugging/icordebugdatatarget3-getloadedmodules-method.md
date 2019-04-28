---
title: ICorDebugDataTarget3::GetLoadedModules 메서드
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 464fd9ac44d6ba5717dbc4ecfbe03b6e6ad52276
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789723"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="1173c-102">ICorDebugDataTarget3::GetLoadedModules 메서드</span><span class="sxs-lookup"><span data-stu-id="1173c-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="1173c-103">지금까지 로드된 모듈 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1173c-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1173c-104">구문</span><span class="sxs-lookup"><span data-stu-id="1173c-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1173c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1173c-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="1173c-106">[in] 정보가 요청된 모듈 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1173c-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="1173c-107">[out] 정보가 반환된 모듈 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1173c-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="1173c-108">[out] 배열에 대 한 포인터 [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) 로드 된 모듈에 대 한 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1173c-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1173c-109">설명</span><span class="sxs-lookup"><span data-stu-id="1173c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1173c-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1173c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1173c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1173c-111">Requirements</span></span>  
 <span data-ttu-id="1173c-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1173c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1173c-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1173c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1173c-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1173c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1173c-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1173c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1173c-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="1173c-116">See also</span></span>

- [<span data-ttu-id="1173c-117">ICorDebugDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1173c-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="1173c-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1173c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
