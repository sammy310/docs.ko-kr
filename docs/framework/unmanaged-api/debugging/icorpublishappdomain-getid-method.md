---
title: ICorPublishAppDomain::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a7541a2093fe877fb84a8a05237f18c4da43c44
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465987"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="18f2d-102">ICorPublishAppDomain::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="18f2d-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="18f2d-103">이 대 한 고유 식별자를 가져옵니다 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18f2d-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="18f2d-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18f2d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18f2d-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="18f2d-106">[out] 응용 프로그램 도메인의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="18f2d-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18f2d-107">설명</span><span class="sxs-lookup"><span data-stu-id="18f2d-107">Remarks</span></span>  
 <span data-ttu-id="18f2d-108">식별자가 포함 하는 프로세스의 범위 내 에서만 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f2d-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f2d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18f2d-109">Requirements</span></span>  
 <span data-ttu-id="18f2d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="18f2d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f2d-111">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="18f2d-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="18f2d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18f2d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18f2d-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f2d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f2d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="18f2d-114">See also</span></span>
- [<span data-ttu-id="18f2d-115">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18f2d-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
