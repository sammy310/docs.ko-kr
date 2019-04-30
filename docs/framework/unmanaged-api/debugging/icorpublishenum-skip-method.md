---
title: ICorPublishEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98892964eb21746580e9115f86fd1be0832d9f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993501"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="41fba-102">ICorPublishEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="41fba-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="41fba-103">열거형에서 항목의 지정된 된 수 만큼 앞으로 커서를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="41fba-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41fba-104">구문</span><span class="sxs-lookup"><span data-stu-id="41fba-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41fba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41fba-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="41fba-106">[in] 커서를 앞으로 이동에 사용 되는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="41fba-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41fba-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41fba-107">Requirements</span></span>  
 <span data-ttu-id="41fba-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="41fba-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41fba-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="41fba-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="41fba-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41fba-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41fba-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41fba-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41fba-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="41fba-112">See also</span></span>

- [<span data-ttu-id="41fba-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41fba-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
