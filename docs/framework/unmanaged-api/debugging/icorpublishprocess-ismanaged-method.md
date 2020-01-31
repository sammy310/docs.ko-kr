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
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790533"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="e9b20-102">ICorPublishProcess::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="e9b20-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="e9b20-103">이 [ICorPublishProcess](icorpublishprocess-interface.md) 에서 참조 하는 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e9b20-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b20-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9b20-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9b20-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9b20-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="e9b20-106">제한이 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e9b20-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="e9b20-107">프로세스에 관리 되는 코드가 있는 경우 값은 `true`입니다. 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b20-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b20-108">주의</span><span class="sxs-lookup"><span data-stu-id="e9b20-108">Remarks</span></span>  
 <span data-ttu-id="e9b20-109">최신 버전의 `ICorPublishProcess`는 관리 코드를 포함 하는 프로세스에만 액세스할 수 있으므로 `IsManaged`는 항상 `true`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9b20-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b20-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9b20-110">Requirements</span></span>  
 <span data-ttu-id="e9b20-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9b20-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b20-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e9b20-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e9b20-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b20-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b20-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b20-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b20-115">참조</span><span class="sxs-lookup"><span data-stu-id="e9b20-115">See also</span></span>

- [<span data-ttu-id="e9b20-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9b20-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
