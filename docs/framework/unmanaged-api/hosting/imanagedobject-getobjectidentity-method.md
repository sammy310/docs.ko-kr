---
description: '자세히 알아보기: IManagedObject:: GetObjectIdentity 메서드'
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
ms.openlocfilehash: 8929819bbf490680b5f3f1f47b9f3b8e830d57ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671167"
---
# <a name="imanagedobjectgetobjectidentity-method"></a><span data-ttu-id="51910-103">IManagedObject::GetObjectIdentity 메서드</span><span class="sxs-lookup"><span data-stu-id="51910-103">IManagedObject::GetObjectIdentity Method</span></span>

<span data-ttu-id="51910-104">이 관리 되는 개체의 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51910-104">Gets the identity of this managed object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51910-105">구문</span><span class="sxs-lookup"><span data-stu-id="51910-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51910-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51910-106">Parameters</span></span>  

 `pBSTRGUID`  
 <span data-ttu-id="51910-107">제한이 개체가 있는 프로세스의 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51910-107">[out] A pointer to the GUID of the process in which the object resides.</span></span>  
  
 `AppDomainID`  
 <span data-ttu-id="51910-108">제한이 개체의 응용 프로그램 도메인 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51910-108">[out] A pointer to the ID of the object's application domain.</span></span>  
  
 `pCCW`  
 <span data-ttu-id="51910-109">제한이 COM 클래식 v-table에서 개체의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51910-109">[out] A pointer to object's index in the COM classic v-table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51910-110">설명</span><span class="sxs-lookup"><span data-stu-id="51910-110">Remarks</span></span>  

 <span data-ttu-id="51910-111">관리 되는 개체의 id는 프로세스 GUID, 응용 프로그램 도메인 ID 및 COM 클래식 v-table의 개체 인덱스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="51910-111">The identity of a managed object includes process GUID, application domain ID, and the object's index in the COM classic v-table.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51910-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51910-112">Requirements</span></span>  

 <span data-ttu-id="51910-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51910-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51910-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="51910-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51910-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51910-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51910-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51910-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51910-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51910-117">See also</span></span>

- [<span data-ttu-id="51910-118">IManagedObject 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51910-118">IManagedObject Interface</span></span>](imanagedobject-interface.md)
