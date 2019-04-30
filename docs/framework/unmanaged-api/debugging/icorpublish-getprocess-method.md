---
title: ICorPublish::GetProcess 메서드
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 021068caa8f1ad2c64e5ca3d18ea25dc827563a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986702"
---
# <a name="icorpublishgetprocess-method"></a><span data-ttu-id="8a498-102">ICorPublish::GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="8a498-102">ICorPublish::GetProcess Method</span></span>
<span data-ttu-id="8a498-103">가져옵니다는 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 지정된 된 식별자를 사용 하 여 프로세스를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a498-103">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a498-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a498-104">Syntax</span></span>  
  
```  
HRESULT GetProcess(  
    [in] unsigned              pid,   
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a498-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8a498-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="8a498-106">[in] 프로세스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8a498-106">[in] The identifier of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="8a498-107">[out] 주소에 대 한 포인터는 `ICorPublishProcess` 프로세스를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a498-107">[out] A pointer to the address of an `ICorPublishProcess` instance that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a498-108">설명</span><span class="sxs-lookup"><span data-stu-id="8a498-108">Remarks</span></span>  
 <span data-ttu-id="8a498-109">`GetProcess` 프로세스가 존재 하지 않는 이거나 현재 사용자가 디버깅할 수 있는 관리 되는 프로세스가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a498-109">`GetProcess` fails if the process doesn't exist, or isn't a managed process that can be debugged by the current user.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a498-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a498-110">Requirements</span></span>  
 <span data-ttu-id="8a498-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a498-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a498-112">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8a498-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8a498-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a498-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a498-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a498-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a498-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a498-115">See also</span></span>

- [<span data-ttu-id="8a498-116">ICorPublish 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a498-116">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
