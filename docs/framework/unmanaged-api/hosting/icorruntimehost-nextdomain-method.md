---
title: ICorRuntimeHost::NextDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139503"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="6ea39-102">ICorRuntimeHost::NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="6ea39-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="6ea39-103">열거형의 다음 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea39-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ea39-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea39-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6ea39-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6ea39-106">진행 [Enumdomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)호출을 통해 가져온 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="6ea39-107">제한이 열거형의 다음 도메인을 나타내는 <xref:System._AppDomain?displayProperty=nameWithType> 형식에 대 한 인터페이스 포인터 이거나, 더 이상 도메인이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ea39-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6ea39-108">Return Value</span></span>  
  
|<span data-ttu-id="6ea39-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ea39-109">HRESULT</span></span>|<span data-ttu-id="6ea39-110">설명</span><span class="sxs-lookup"><span data-stu-id="6ea39-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ea39-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ea39-111">S_OK</span></span>|<span data-ttu-id="6ea39-112">작업에 성공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-112">The operation was successful.</span></span>|  
|<span data-ttu-id="6ea39-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6ea39-113">S_FALSE</span></span>|<span data-ttu-id="6ea39-114">작업을 완료 하지 못했거나 열거에 도메인이 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="6ea39-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6ea39-115">E_FAIL</span></span>|<span data-ttu-id="6ea39-116">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6ea39-117">메서드가 E_FAIL을 반환 하는 경우 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6ea39-118">모든 호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6ea39-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6ea39-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6ea39-120">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6ea39-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6ea39-121">Requirements</span></span>  
 <span data-ttu-id="6ea39-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea39-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea39-123">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6ea39-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ea39-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ea39-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ea39-125">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="6ea39-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea39-126">참조</span><span class="sxs-lookup"><span data-stu-id="6ea39-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="6ea39-127">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6ea39-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
