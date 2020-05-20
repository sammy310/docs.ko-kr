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
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615867"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="87d96-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="87d96-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="87d96-103">제공 된 이름이 목록의 어셈블리 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d96-104">구문</span><span class="sxs-lookup"><span data-stu-id="87d96-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d96-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87d96-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="87d96-106">진행 검색할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87d96-107">Return Value</span><span class="sxs-lookup"><span data-stu-id="87d96-107">Return Value</span></span>  
  
|<span data-ttu-id="87d96-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87d96-108">HRESULT</span></span>|<span data-ttu-id="87d96-109">설명</span><span class="sxs-lookup"><span data-stu-id="87d96-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87d96-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87d96-110">S_OK</span></span>|<span data-ttu-id="87d96-111">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="87d96-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="87d96-112">S_FALSE</span></span>|<span data-ttu-id="87d96-113">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="87d96-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87d96-114">E_FAIL</span></span>|<span data-ttu-id="87d96-115">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87d96-116">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="87d96-117">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87d96-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87d96-118">Requirements</span></span>  
 <span data-ttu-id="87d96-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87d96-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d96-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="87d96-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87d96-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87d96-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87d96-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d96-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d96-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87d96-123">See also</span></span>

- [<span data-ttu-id="87d96-124">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87d96-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="87d96-125">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87d96-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="87d96-126">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87d96-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="87d96-127">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87d96-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
