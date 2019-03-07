---
title: GetAssemblyIdentityFromFile 함수
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20ea800b86a169eff984b6068db3e9887235a034
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496978"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="0a0e3-102">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="0a0e3-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="0a0e3-103">포인터를 가져는 `IUnknown` 지정 된 개체 `IID` 지정된 된 파일 경로에 있는 어셈블리에서.</span><span class="sxs-lookup"><span data-stu-id="0a0e3-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a0e3-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a0e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a0e3-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="0a0e3-106">[in] 요청된 된 어셈블리에 대 한 유효한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e3-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="0a0e3-107">[in] `IID` 반환할 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e3-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="0a0e3-108">[out] 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a0e3-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0e3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a0e3-109">Requirements</span></span>  
 <span data-ttu-id="0a0e3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0a0e3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0e3-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0a0e3-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0a0e3-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0e3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0e3-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a0e3-113">See also</span></span>
- [<span data-ttu-id="0a0e3-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="0a0e3-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="0a0e3-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="0a0e3-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
