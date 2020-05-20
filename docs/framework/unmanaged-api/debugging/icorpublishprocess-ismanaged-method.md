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
ms.openlocfilehash: 3eec84624866b2be7068d7875cd650828c283fd2
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421100"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="1d2e4-102">ICorPublishProcess::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="1d2e4-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="1d2e4-103">이 [ICorPublishProcess](icorpublishprocess-interface.md) 에서 참조 하는 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d2e4-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d2e4-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d2e4-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d2e4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d2e4-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="1d2e4-106">제한이 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2e4-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="1d2e4-107">`true`프로세스에 관리 되는 코드가 있으면 값이이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1d2e4-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d2e4-108">설명</span><span class="sxs-lookup"><span data-stu-id="1d2e4-108">Remarks</span></span>  
 <span data-ttu-id="1d2e4-109">현재 버전의에서는 `ICorPublishProcess` 관리 코드가 있는 프로세스에 대 한 액세스만 허용 하므로는 `IsManaged` 항상를 반환 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d2e4-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d2e4-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d2e4-110">Requirements</span></span>  
 <span data-ttu-id="1d2e4-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d2e4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d2e4-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="1d2e4-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1d2e4-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d2e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d2e4-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d2e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2e4-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d2e4-115">See also</span></span>

- [<span data-ttu-id="1d2e4-116">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d2e4-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
