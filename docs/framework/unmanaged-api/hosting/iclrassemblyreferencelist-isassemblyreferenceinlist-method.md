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
ms.openlocfilehash: f74e0f111ff7869d0bfed61d420f3788f65876dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679158"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="88369-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="88369-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>

<span data-ttu-id="88369-103">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88369-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88369-104">구문</span><span class="sxs-lookup"><span data-stu-id="88369-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88369-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88369-105">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="88369-106">진행 검색할 어셈블리에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88369-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="88369-107">유효한 값은 또는 형식 `IAssemblyName` 입니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="88369-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88369-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="88369-108">Return Value</span></span>  
  
|<span data-ttu-id="88369-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88369-109">HRESULT</span></span>|<span data-ttu-id="88369-110">설명</span><span class="sxs-lookup"><span data-stu-id="88369-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88369-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="88369-111">S_OK</span></span>|<span data-ttu-id="88369-112">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88369-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="88369-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="88369-113">S_FALSE</span></span>|<span data-ttu-id="88369-114">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88369-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="88369-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="88369-115">E_FAIL</span></span>|<span data-ttu-id="88369-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="88369-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="88369-117">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88369-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="88369-118">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88369-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88369-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88369-119">Requirements</span></span>  

 <span data-ttu-id="88369-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88369-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88369-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="88369-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88369-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88369-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88369-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88369-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88369-124">참조</span><span class="sxs-lookup"><span data-stu-id="88369-124">See also</span></span>

- [<span data-ttu-id="88369-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88369-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="88369-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88369-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="88369-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88369-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="88369-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88369-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
