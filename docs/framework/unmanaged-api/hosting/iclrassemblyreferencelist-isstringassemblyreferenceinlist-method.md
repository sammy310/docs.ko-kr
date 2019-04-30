---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969912"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="25ed4-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="25ed4-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="25ed4-103">제공 된 이름 목록에 있는 어셈블리의 이름을 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25ed4-104">구문</span><span class="sxs-lookup"><span data-stu-id="25ed4-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25ed4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25ed4-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="25ed4-106">[in] 검색할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25ed4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="25ed4-107">Return Value</span></span>  
  
|<span data-ttu-id="25ed4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25ed4-108">HRESULT</span></span>|<span data-ttu-id="25ed4-109">설명</span><span class="sxs-lookup"><span data-stu-id="25ed4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25ed4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="25ed4-110">S_OK</span></span>|<span data-ttu-id="25ed4-111">문자열 목록에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="25ed4-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="25ed4-112">S_FALSE</span></span>|<span data-ttu-id="25ed4-113">문자열 목록에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="25ed4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25ed4-114">E_FAIL</span></span>|<span data-ttu-id="25ed4-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="25ed4-116">메서드 E_FAIL을 반환 하는 경우 공용 언어 런타임에서 더 이상 프로세스 내에서 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="25ed4-117">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ed4-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25ed4-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25ed4-118">Requirements</span></span>  
 <span data-ttu-id="25ed4-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="25ed4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ed4-120">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25ed4-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25ed4-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="25ed4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25ed4-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25ed4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ed4-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="25ed4-123">See also</span></span>

- [<span data-ttu-id="25ed4-124">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ed4-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="25ed4-125">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ed4-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="25ed4-126">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ed4-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="25ed4-127">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25ed4-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
