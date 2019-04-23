---
title: IManagedObject::GetObjectIdentity 메서드
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d014d2900ea790f84331ed933143513ae9e63f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213495"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="25dca-102">IManagedObject::GetObjectIdentity 메서드</span><span class="sxs-lookup"><span data-stu-id="25dca-102">IManagedObject::GetObjectIdentity Method</span></span>
<span data-ttu-id="25dca-103">이 관리 되는 개체의 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25dca-103">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25dca-104">구문</span><span class="sxs-lookup"><span data-stu-id="25dca-104">Syntax</span></span>  
  
```  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25dca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25dca-105">Parameters</span></span>  
 `pBSTRGUID`  
 <span data-ttu-id="25dca-106">[out] 개체가 상주 하는 프로세스의 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25dca-106">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="25dca-107">[out] 개체의 응용 프로그램 도메인의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25dca-107">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="25dca-108">[out] COM 클래식 v-table에서 개체의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="25dca-108">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25dca-109">설명</span><span class="sxs-lookup"><span data-stu-id="25dca-109">Remarks</span></span>  
 <span data-ttu-id="25dca-110">COM 클래식 v 테이블에서 프로세스 GUID, 응용 프로그램 도메인 ID 및 개체의 인덱스를 포함 하는 관리 되는 개체의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="25dca-110">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25dca-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25dca-111">Requirements</span></span>  
 <span data-ttu-id="25dca-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="25dca-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25dca-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25dca-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25dca-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="25dca-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25dca-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25dca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25dca-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="25dca-116">See also</span></span>

- [<span data-ttu-id="25dca-117">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25dca-117">IManagedObject Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)
