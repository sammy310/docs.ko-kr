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
ms.openlocfilehash: 29427bab938437c40d0edb5676a2f8f76cbb6691
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764866"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="675d6-102">ICorPublishProcess::GetProcessID 메서드</span><span class="sxs-lookup"><span data-stu-id="675d6-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="675d6-103">이 프로세스에 대 한 운영 체제 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="675d6-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="675d6-104">구문</span><span class="sxs-lookup"><span data-stu-id="675d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="675d6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="675d6-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="675d6-106">[out] 이 나타내는 프로세스의 식별자에 대 한 포인터 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="675d6-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="675d6-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="675d6-107">Requirements</span></span>  
 <span data-ttu-id="675d6-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="675d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="675d6-109">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="675d6-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="675d6-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="675d6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="675d6-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="675d6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="675d6-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="675d6-112">See also</span></span>

- [<span data-ttu-id="675d6-113">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="675d6-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
