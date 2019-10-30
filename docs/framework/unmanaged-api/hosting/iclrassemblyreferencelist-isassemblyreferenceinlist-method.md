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
ms.openlocfilehash: 4e75b8553ff33946654a6a3b6184f98049c6a6cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126674"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="625c6-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="625c6-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="625c6-103">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="625c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="625c6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="625c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="625c6-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="625c6-106">진행 검색할 어셈블리에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="625c6-107">유효한 값은 `IAssemblyName` 또는 `IReferenceIdentity`유형입니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="625c6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="625c6-108">Return Value</span></span>  
  
|<span data-ttu-id="625c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="625c6-109">HRESULT</span></span>|<span data-ttu-id="625c6-110">설명</span><span class="sxs-lookup"><span data-stu-id="625c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="625c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="625c6-111">S_OK</span></span>|<span data-ttu-id="625c6-112">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="625c6-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="625c6-113">S_FALSE</span></span>|<span data-ttu-id="625c6-114">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="625c6-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="625c6-115">E_FAIL</span></span>|<span data-ttu-id="625c6-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="625c6-117">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="625c6-118">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="625c6-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="625c6-119">Requirements</span></span>  
 <span data-ttu-id="625c6-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="625c6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="625c6-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="625c6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="625c6-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="625c6-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="625c6-123">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="625c6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="625c6-124">참조</span><span class="sxs-lookup"><span data-stu-id="625c6-124">See also</span></span>

- [<span data-ttu-id="625c6-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="625c6-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="625c6-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="625c6-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="625c6-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="625c6-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="625c6-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="625c6-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
