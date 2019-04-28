---
title: CreateAssemblyCache 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf78ded62f11b336d9f5fe0f3a205275ae37189b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669990"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="f7352-102">CreateAssemblyCache 함수</span><span class="sxs-lookup"><span data-stu-id="f7352-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="f7352-103">새 포인터를 가져옵니다 [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) 전역 어셈블리 캐시를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="f7352-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7352-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7352-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7352-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7352-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="f7352-106">[out] 반환 된 `IAssemblyCache` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f7352-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="f7352-107">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7352-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="f7352-108">`dwReserved` 0 (영) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7352-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7352-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7352-109">Requirements</span></span>  
 <span data-ttu-id="f7352-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7352-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7352-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f7352-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f7352-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f7352-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7352-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7352-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7352-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7352-114">See also</span></span>

- [<span data-ttu-id="f7352-115">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7352-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="f7352-116">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f7352-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="f7352-117">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="f7352-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
