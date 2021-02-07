---
description: '자세히 알아보기: ICLRAssemblyReferenceList:: IsAssemblyReferenceInList 메서드'
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
ms.openlocfilehash: ce90423715d6cbe07c1112cb2136c11fd58c982a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716772"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="61d4d-103">ICLRAssemblyReferenceList::IsAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="61d4d-103">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>

<span data-ttu-id="61d4d-104">제공 된 포인터가 목록의 어셈블리를 참조 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-104">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d4d-105">구문</span><span class="sxs-lookup"><span data-stu-id="61d4d-105">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61d4d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61d4d-106">Parameters</span></span>  

 `pName`  
 <span data-ttu-id="61d4d-107">진행 검색할 어셈블리에 대 한 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-107">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="61d4d-108">유효한 값은 또는 형식 `IAssemblyName` 입니다 `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="61d4d-108">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61d4d-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="61d4d-109">Return Value</span></span>  
  
|<span data-ttu-id="61d4d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61d4d-110">HRESULT</span></span>|<span data-ttu-id="61d4d-111">설명</span><span class="sxs-lookup"><span data-stu-id="61d4d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61d4d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="61d4d-112">S_OK</span></span>|<span data-ttu-id="61d4d-113">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-113">The string appears in the list.</span></span>|  
|<span data-ttu-id="61d4d-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="61d4d-114">S_FALSE</span></span>|<span data-ttu-id="61d4d-115">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-115">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="61d4d-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61d4d-116">E_FAIL</span></span>|<span data-ttu-id="61d4d-117">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-117">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61d4d-118">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-118">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="61d4d-119">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-119">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61d4d-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61d4d-120">Requirements</span></span>  

 <span data-ttu-id="61d4d-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61d4d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61d4d-122">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="61d4d-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61d4d-123">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61d4d-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61d4d-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61d4d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d4d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61d4d-125">See also</span></span>

- [<span data-ttu-id="61d4d-126">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61d4d-126">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="61d4d-127">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61d4d-127">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="61d4d-128">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61d4d-128">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="61d4d-129">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61d4d-129">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
