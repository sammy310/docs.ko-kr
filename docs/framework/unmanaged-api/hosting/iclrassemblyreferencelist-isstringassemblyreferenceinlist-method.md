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
ms.openlocfilehash: 4dc91723f009d46f9c57b1c99aa66ba7a1b127e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126639"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="64fd5-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="64fd5-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="64fd5-103">제공 된 이름이 목록의 어셈블리 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64fd5-104">구문</span><span class="sxs-lookup"><span data-stu-id="64fd5-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64fd5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64fd5-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="64fd5-106">진행 검색할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64fd5-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="64fd5-107">Return Value</span></span>  
  
|<span data-ttu-id="64fd5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64fd5-108">HRESULT</span></span>|<span data-ttu-id="64fd5-109">설명</span><span class="sxs-lookup"><span data-stu-id="64fd5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64fd5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="64fd5-110">S_OK</span></span>|<span data-ttu-id="64fd5-111">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="64fd5-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="64fd5-112">S_FALSE</span></span>|<span data-ttu-id="64fd5-113">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="64fd5-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64fd5-114">E_FAIL</span></span>|<span data-ttu-id="64fd5-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64fd5-116">메서드가 E_FAIL을 반환한 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="64fd5-117">호스팅 메서드에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64fd5-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64fd5-118">Requirements</span></span>  
 <span data-ttu-id="64fd5-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64fd5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64fd5-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="64fd5-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64fd5-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64fd5-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64fd5-122">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64fd5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64fd5-123">참조</span><span class="sxs-lookup"><span data-stu-id="64fd5-123">See also</span></span>

- [<span data-ttu-id="64fd5-124">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64fd5-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="64fd5-125">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64fd5-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="64fd5-126">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64fd5-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="64fd5-127">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64fd5-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
