---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de166a22350e49197ff6a5b5d6dc956cdcc2d1ac
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985142"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="af8c2-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 메서드</span><span class="sxs-lookup"><span data-stu-id="af8c2-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="af8c2-103">한 인터페이스 포인터를 가져옵니다는 [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) 부분 어셈블리 id의 제공 된 목록에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="af8c2-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af8c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="af8c2-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af8c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af8c2-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="af8c2-106">[in] 배열 형식으로 null로 끝나는 문자열의 "이름, 속성 = value..." 부분 어셈블리 id의 목록을 지정 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="af8c2-107">[in] 항목 수가 `ppwzAssemblyReferences`합니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="af8c2-108">[out] 에 대 한 인터페이스 포인터를 `ICLRAssemblyReferenceList` 에 지정 된 어셈블리 목록에 대 한 어셈블리 id 데이터를 포함 하는 개체 `ppwzAssemblyReferences`합니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af8c2-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="af8c2-109">Return Value</span></span>  
  
|<span data-ttu-id="af8c2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af8c2-110">HRESULT</span></span>|<span data-ttu-id="af8c2-111">설명</span><span class="sxs-lookup"><span data-stu-id="af8c2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af8c2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="af8c2-112">S_OK</span></span>|<span data-ttu-id="af8c2-113">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="af8c2-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="af8c2-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af8c2-115">프로세스에는 CLR (공용 언어 런타임)에 로드 되지 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af8c2-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af8c2-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af8c2-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-117">The call timed out.</span></span>|  
|<span data-ttu-id="af8c2-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af8c2-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af8c2-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af8c2-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af8c2-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af8c2-121">이벤트가 차단 된 스레드가 취소 된 또는 파이버를 대기 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af8c2-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af8c2-122">E_FAIL</span></span>|<span data-ttu-id="af8c2-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af8c2-124">메서드가 E_FAIL을 반환 하는 경우 CLR은 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af8c2-125">메서드를 호스트 하는 데 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af8c2-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af8c2-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af8c2-126">Requirements</span></span>  
 <span data-ttu-id="af8c2-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="af8c2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af8c2-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af8c2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af8c2-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="af8c2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af8c2-130">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af8c2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af8c2-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="af8c2-131">See also</span></span>

- [<span data-ttu-id="af8c2-132">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af8c2-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="af8c2-133">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af8c2-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
