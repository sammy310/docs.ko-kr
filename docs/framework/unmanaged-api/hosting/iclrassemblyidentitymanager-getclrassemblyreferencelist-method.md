---
description: '자세히 알아보기: ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList 메서드'
title: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 메서드
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
ms.openlocfilehash: 91f7b9eaacee559c5e404b5dda0f8b4201f91a66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649561"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="804a0-103">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 메서드</span><span class="sxs-lookup"><span data-stu-id="804a0-103">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="804a0-104">제공 된 부분 어셈블리 id 목록에서 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-104">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="804a0-105">구문</span><span class="sxs-lookup"><span data-stu-id="804a0-105">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="804a0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="804a0-106">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="804a0-107">진행 "Name, property = value ..." 형식으로 된 null로 끝나는 문자열의 배열입니다. 부분 어셈블리 id 목록을 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-107">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="804a0-108">진행 의 항목 수 `ppwzAssemblyReferences` 입니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-108">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="804a0-109">제한이 `ICLRAssemblyReferenceList` 에 지정 된 어셈블리 목록에 대 한 어셈블리 id 데이터를 포함 하는 개체에 대 한 인터페이스 포인터입니다 `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="804a0-109">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="804a0-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="804a0-110">Return Value</span></span>  
  
|<span data-ttu-id="804a0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="804a0-111">HRESULT</span></span>|<span data-ttu-id="804a0-112">설명</span><span class="sxs-lookup"><span data-stu-id="804a0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="804a0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="804a0-113">S_OK</span></span>|<span data-ttu-id="804a0-114">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-114">The method returned successfully.</span></span>|  
|<span data-ttu-id="804a0-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="804a0-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="804a0-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="804a0-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="804a0-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="804a0-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-118">The call timed out.</span></span>|  
|<span data-ttu-id="804a0-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="804a0-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="804a0-120">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="804a0-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="804a0-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="804a0-122">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="804a0-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="804a0-123">E_FAIL</span></span>|<span data-ttu-id="804a0-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="804a0-125">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-125">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="804a0-126">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="804a0-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="804a0-127">Requirements</span></span>  

 <span data-ttu-id="804a0-128">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="804a0-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="804a0-129">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="804a0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="804a0-130">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="804a0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="804a0-131">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="804a0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="804a0-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="804a0-132">See also</span></span>

- [<span data-ttu-id="804a0-133">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="804a0-133">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="804a0-134">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="804a0-134">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
