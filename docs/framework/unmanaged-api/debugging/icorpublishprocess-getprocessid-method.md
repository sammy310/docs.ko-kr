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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f3948e45b991e667ea90c7846ee0d6fd630c0db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165804"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="793a1-102">ICorPublishProcess::GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="793a1-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="793a1-103">이 프로세스에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="793a1-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="793a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="793a1-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="793a1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="793a1-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="793a1-106">[out] 이 나타내는 프로세스의 식별자에 대 한 포인터 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="793a1-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="793a1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="793a1-107">Requirements</span></span>  
 <span data-ttu-id="793a1-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="793a1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="793a1-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="793a1-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="793a1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="793a1-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="793a1-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="793a1-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="793a1-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="793a1-112">See also</span></span>

- [<span data-ttu-id="793a1-113">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="793a1-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
