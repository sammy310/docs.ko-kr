---
description: '자세히 알아보기: ICLRAssemblyReferenceList:: IsStringAssemblyReferenceInList 메서드'
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
ms.openlocfilehash: 667764337fbda22a526e51575faf049efc4b86ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790037"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="c69ba-103">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList 메서드</span><span class="sxs-lookup"><span data-stu-id="c69ba-103">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>

<span data-ttu-id="c69ba-104">제공 된 이름이 목록의 어셈블리 이름과 일치 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-104">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c69ba-105">구문</span><span class="sxs-lookup"><span data-stu-id="c69ba-105">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c69ba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c69ba-106">Parameters</span></span>  

 `pwzAssemblyName`  
 <span data-ttu-id="c69ba-107">진행 검색할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-107">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c69ba-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="c69ba-108">Return Value</span></span>  
  
|<span data-ttu-id="c69ba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c69ba-109">HRESULT</span></span>|<span data-ttu-id="c69ba-110">설명</span><span class="sxs-lookup"><span data-stu-id="c69ba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c69ba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c69ba-111">S_OK</span></span>|<span data-ttu-id="c69ba-112">문자열은 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="c69ba-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c69ba-113">S_FALSE</span></span>|<span data-ttu-id="c69ba-114">문자열은 목록에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="c69ba-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c69ba-115">E_FAIL</span></span>|<span data-ttu-id="c69ba-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c69ba-117">메서드가 E_FAIL 반환 된 후에는 프로세스 내에서 공용 언어 런타임을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="c69ba-118">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c69ba-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c69ba-119">Requirements</span></span>  

 <span data-ttu-id="c69ba-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c69ba-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c69ba-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c69ba-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c69ba-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c69ba-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c69ba-123">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c69ba-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69ba-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c69ba-124">See also</span></span>

- [<span data-ttu-id="c69ba-125">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c69ba-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c69ba-126">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c69ba-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c69ba-127">IHostAssemblyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c69ba-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="c69ba-128">IHostAssemblyStore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c69ba-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
