---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6a95a636623f0b4ea75706039194572ecf1bbe0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136203"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="7a2a2-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="7a2a2-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="7a2a2-103">제공 된 포인터 목록에 있는 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a2a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="7a2a2-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a2a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a2a2-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="7a2a2-106">[in] 검색할 어셈블리에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="7a2a2-107">유효한 값은 형식의 `IAssemblyName` 또는 `IReferenceIdentity`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a2a2-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="7a2a2-108">Return Value</span></span>  
  
|<span data-ttu-id="7a2a2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a2a2-109">HRESULT</span></span>|<span data-ttu-id="7a2a2-110">설명</span><span class="sxs-lookup"><span data-stu-id="7a2a2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a2a2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a2a2-111">S_OK</span></span>|<span data-ttu-id="7a2a2-112">문자열 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="7a2a2-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7a2a2-113">S_FALSE</span></span>|<span data-ttu-id="7a2a2-114">문자열 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="7a2a2-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a2a2-115">E_FAIL</span></span>|<span data-ttu-id="7a2a2-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a2a2-117">메서드 E_FAIL을 반환 하는 경우 공용 언어 런타임에서 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="7a2a2-118">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a2a2-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a2a2-119">Requirements</span></span>  
 <span data-ttu-id="7a2a2-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7a2a2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2a2-121">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a2a2-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a2a2-122">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7a2a2-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="7a2a2-123">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7a2a2-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a2a2-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="7a2a2-124">See also</span></span>

- [<span data-ttu-id="7a2a2-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a2a2-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="7a2a2-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a2a2-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="7a2a2-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a2a2-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="7a2a2-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a2a2-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
