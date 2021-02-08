---
description: '자세히 알아보기: ICorRuntimeHost:: NextDomain 메서드'
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
ms.openlocfilehash: cfced9d1d3c91f4ec9508b86157ceebae9f95a56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789621"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="0b3f6-103">ICorRuntimeHost::NextDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="0b3f6-103">ICorRuntimeHost::NextDomain Method</span></span>

<span data-ttu-id="0b3f6-104">열거형의 다음 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-104">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b3f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="0b3f6-105">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b3f6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0b3f6-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="0b3f6-107">진행 [Enumdomains](icorruntimehost-enumdomains-method.md)호출을 통해 가져온 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-107">[in] The enumerator that was obtained through a call to [EnumDomains](icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0b3f6-108">제한이 <xref:System._AppDomain?displayProperty=nameWithType> 열거형의 다음 도메인을 나타내는 형식에 대 한 인터페이스 포인터 이거나, 더 이상 도메인이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-108">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b3f6-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="0b3f6-109">Return Value</span></span>  
  
|<span data-ttu-id="0b3f6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b3f6-110">HRESULT</span></span>|<span data-ttu-id="0b3f6-111">설명</span><span class="sxs-lookup"><span data-stu-id="0b3f6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b3f6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b3f6-112">S_OK</span></span>|<span data-ttu-id="0b3f6-113">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-113">The operation was successful.</span></span>|  
|<span data-ttu-id="0b3f6-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0b3f6-114">S_FALSE</span></span>|<span data-ttu-id="0b3f6-115">작업을 완료 하지 못했거나 열거에 도메인이 더 이상 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-115">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="0b3f6-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b3f6-116">E_FAIL</span></span>|<span data-ttu-id="0b3f6-117">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0b3f6-118">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="0b3f6-119">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0b3f6-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b3f6-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b3f6-121">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b3f6-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0b3f6-122">Requirements</span></span>  

 <span data-ttu-id="0b3f6-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b3f6-124">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0b3f6-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b3f6-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b3f6-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b3f6-126">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0b3f6-126">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b3f6-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b3f6-127">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="0b3f6-128">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0b3f6-128">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
