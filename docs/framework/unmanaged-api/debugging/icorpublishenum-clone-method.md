---
title: ICorPublishEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: afd16f1f31be9148422dd6d0be748036a8e5d99a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790655"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="e1c10-102">ICorPublishEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="e1c10-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="e1c10-103">이 [ICorPublishEnum](icorpublishenum-interface.md) 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e1c10-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c10-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1c10-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1c10-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1c10-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e1c10-106">제한이 이 `ICorPublishEnum` 개체의 복사본 인 `ICorPublishEnum` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1c10-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1c10-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1c10-107">Requirements</span></span>  
 <span data-ttu-id="e1c10-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e1c10-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1c10-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e1c10-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e1c10-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1c10-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1c10-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c10-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c10-112">참조</span><span class="sxs-lookup"><span data-stu-id="e1c10-112">See also</span></span>

- [<span data-ttu-id="e1c10-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1c10-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
