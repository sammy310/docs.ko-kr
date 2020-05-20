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
ms.openlocfilehash: 0632a7f5feee87c386d9488a6c989413af68a47f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615893"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="5d9bf-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="5d9bf-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="5d9bf-103">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d9bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d9bf-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d9bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d9bf-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="5d9bf-106">진행 검색할 어셈블리에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="5d9bf-107">유효한 값은 또는 형식 `IAssemblyName` 입니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="5d9bf-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d9bf-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="5d9bf-108">Return Value</span></span>  
  
|<span data-ttu-id="5d9bf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d9bf-109">HRESULT</span></span>|<span data-ttu-id="5d9bf-110">설명</span><span class="sxs-lookup"><span data-stu-id="5d9bf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d9bf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d9bf-111">S_OK</span></span>|<span data-ttu-id="5d9bf-112">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="5d9bf-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5d9bf-113">S_FALSE</span></span>|<span data-ttu-id="5d9bf-114">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="5d9bf-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d9bf-115">E_FAIL</span></span>|<span data-ttu-id="5d9bf-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d9bf-117">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="5d9bf-118">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d9bf-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d9bf-119">Requirements</span></span>  
 <span data-ttu-id="5d9bf-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d9bf-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="5d9bf-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d9bf-122">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d9bf-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d9bf-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d9bf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d9bf-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d9bf-124">See also</span></span>

- [<span data-ttu-id="5d9bf-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d9bf-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5d9bf-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d9bf-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5d9bf-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d9bf-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="5d9bf-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d9bf-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
