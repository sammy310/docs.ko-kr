---
title: ICorPublishProcess::GetProcessID 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: 728e8bdbce7f93176324d8f80261030f8cbae283
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140411"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="af664-102">ICorPublishProcess::GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="af664-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="af664-103">이 프로세스에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="af664-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af664-104">구문</span><span class="sxs-lookup"><span data-stu-id="af664-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af664-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af664-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="af664-106">제한이 이 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 개체가 나타내는 프로세스의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="af664-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af664-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af664-107">Requirements</span></span>  
 <span data-ttu-id="af664-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af664-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af664-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="af664-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="af664-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af664-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af664-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af664-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af664-112">참조</span><span class="sxs-lookup"><span data-stu-id="af664-112">See also</span></span>

- [<span data-ttu-id="af664-113">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af664-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
