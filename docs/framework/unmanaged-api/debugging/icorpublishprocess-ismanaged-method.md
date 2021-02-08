---
description: '자세히 알아보기: ICorPublishProcess:: IsManaged 메서드'
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
ms.openlocfilehash: 55f620a896efd87c2f154ac68ef2db1a1b0a1ebc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790505"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="90e1b-103">ICorPublishProcess::IsManaged 메서드</span><span class="sxs-lookup"><span data-stu-id="90e1b-103">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="90e1b-104">이 [ICorPublishProcess](icorpublishprocess-interface.md) 에서 참조 하는 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90e1b-104">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e1b-105">구문</span><span class="sxs-lookup"><span data-stu-id="90e1b-105">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90e1b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90e1b-106">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="90e1b-107">제한이 프로세스에 관리 되는 코드가 있는지 여부를 나타내는 부울 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90e1b-107">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="90e1b-108">`true`프로세스에 관리 되는 코드가 있으면 값이이 고, 그렇지 않으면 `false` 입니다.</span><span class="sxs-lookup"><span data-stu-id="90e1b-108">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90e1b-109">설명</span><span class="sxs-lookup"><span data-stu-id="90e1b-109">Remarks</span></span>  

 <span data-ttu-id="90e1b-110">현재 버전의에서는 `ICorPublishProcess` 관리 코드가 있는 프로세스에 대 한 액세스만 허용 하므로는 `IsManaged` 항상를 반환 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="90e1b-110">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e1b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90e1b-111">Requirements</span></span>  

 <span data-ttu-id="90e1b-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="90e1b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e1b-113">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="90e1b-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="90e1b-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90e1b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90e1b-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e1b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90e1b-116">See also</span></span>

- [<span data-ttu-id="90e1b-117">ICorPublishProcess 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90e1b-117">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
