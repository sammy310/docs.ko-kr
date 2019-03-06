---
title: ICorPublishProcess::IsManaged 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 404403576b7fd32362a690d470a5ea4b48489d26
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484799"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="67c81-102">ICorPublishProcess::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="67c81-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="67c81-103">이 프로세스를 참조 하는지 여부를 나타내는 값을 가져옵니다 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 에 있을 경우 관리 코드 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67c81-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c81-104">구문</span><span class="sxs-lookup"><span data-stu-id="67c81-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67c81-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="67c81-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="67c81-106">[out] 프로세스에 코드를 관리 하는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="67c81-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="67c81-107">값이 `true` 프로세스에 코드를 관리 하는 경우이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="67c81-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c81-108">설명</span><span class="sxs-lookup"><span data-stu-id="67c81-108">Remarks</span></span>  
 <span data-ttu-id="67c81-109">현재 버전의 이후 `ICorPublishProcess` 코드를 관리 하는 프로세스에만 액세스할 수 있습니다 `IsManaged` 항상 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="67c81-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c81-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="67c81-110">Requirements</span></span>  
 <span data-ttu-id="67c81-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67c81-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c81-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="67c81-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="67c81-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67c81-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67c81-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c81-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c81-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="67c81-115">See also</span></span>
- [<span data-ttu-id="67c81-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="67c81-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
