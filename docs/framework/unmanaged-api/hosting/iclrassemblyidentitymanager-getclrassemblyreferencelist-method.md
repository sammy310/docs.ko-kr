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
ms.openlocfilehash: cfc384a71ac7e91181bdec09f0d385bacbe31753
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716670"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="188a5-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList 메서드</span><span class="sxs-lookup"><span data-stu-id="188a5-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>

<span data-ttu-id="188a5-103">제공 된 부분 어셈블리 id 목록에서 [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="188a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="188a5-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="188a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="188a5-105">Parameters</span></span>  

 `ppwzAssemblyReferences`  
 <span data-ttu-id="188a5-106">진행 "Name, property = value ..." 형식으로 된 null로 끝나는 문자열의 배열입니다. 부분 어셈블리 id 목록을 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="188a5-107">진행 의 항목 수 `ppwzAssemblyReferences` 입니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="188a5-108">제한이 `ICLRAssemblyReferenceList` 에 지정 된 어셈블리 목록에 대 한 어셈블리 id 데이터를 포함 하는 개체에 대 한 인터페이스 포인터입니다 `ppwzAssemblyReferences` .</span><span class="sxs-lookup"><span data-stu-id="188a5-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="188a5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="188a5-109">Return Value</span></span>  
  
|<span data-ttu-id="188a5-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="188a5-110">HRESULT</span></span>|<span data-ttu-id="188a5-111">설명</span><span class="sxs-lookup"><span data-stu-id="188a5-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="188a5-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="188a5-112">S_OK</span></span>|<span data-ttu-id="188a5-113">메서드가 성공적으로 반환했습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="188a5-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="188a5-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="188a5-115">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="188a5-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="188a5-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="188a5-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-117">The call timed out.</span></span>|  
|<span data-ttu-id="188a5-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="188a5-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="188a5-119">호출자가 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="188a5-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="188a5-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="188a5-121">차단 된 스레드나 파이버에서 대기 하는 동안 이벤트를 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="188a5-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="188a5-122">E_FAIL</span></span>|<span data-ttu-id="188a5-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="188a5-124">메서드가 E_FAIL 반환 하는 경우 해당 프로세스 내에서 더 이상 CLR을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="188a5-125">호스팅 메서드를 이후에 호출 하면 HOST_E_CLRNOTAVAILABLE 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="188a5-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="188a5-126">Requirements</span></span>  

 <span data-ttu-id="188a5-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="188a5-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="188a5-128">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="188a5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="188a5-129">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="188a5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="188a5-130">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="188a5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188a5-131">참조</span><span class="sxs-lookup"><span data-stu-id="188a5-131">See also</span></span>

- [<span data-ttu-id="188a5-132">ICLRAssemblyIdentityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="188a5-132">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="188a5-133">ICLRAssemblyReferenceList 인터페이스</span><span class="sxs-lookup"><span data-stu-id="188a5-133">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
