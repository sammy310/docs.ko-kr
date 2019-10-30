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
ms.openlocfilehash: ad3a357a98cb5ed28a34e4076b5e145903ceaf91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103492"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="924b0-102">ICorPublishProcess::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="924b0-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="924b0-103">이 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 에서 참조 하는 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="924b0-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="924b0-104">구문</span><span class="sxs-lookup"><span data-stu-id="924b0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="924b0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="924b0-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="924b0-106">제한이 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="924b0-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="924b0-107">프로세스에 관리 되는 코드가 있는 경우 값은 `true`입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="924b0-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="924b0-108">주의</span><span class="sxs-lookup"><span data-stu-id="924b0-108">Remarks</span></span>  
 <span data-ttu-id="924b0-109">최신 버전의 `ICorPublishProcess`는 관리 코드를 포함 하는 프로세스에만 액세스할 수 있으므로 `IsManaged`는 항상 `true`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="924b0-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="924b0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="924b0-110">Requirements</span></span>  
 <span data-ttu-id="924b0-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="924b0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="924b0-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="924b0-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="924b0-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="924b0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="924b0-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="924b0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="924b0-115">참조</span><span class="sxs-lookup"><span data-stu-id="924b0-115">See also</span></span>

- [<span data-ttu-id="924b0-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="924b0-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
