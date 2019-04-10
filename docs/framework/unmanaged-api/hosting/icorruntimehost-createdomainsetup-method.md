---
title: ICorRuntimeHost::CreateDomainSetup 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f5de9882f8a029769d0ccbdac21aec541582a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157367"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="7bc87-102">ICorRuntimeHost::CreateDomainSetup 메서드</span><span class="sxs-lookup"><span data-stu-id="7bc87-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="7bc87-103">인터페이스 포인터의 형식에 IAppDomainSetup 가져옵니다는 <xref:System.AppDomainSetup?displayProperty=nameWithType> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7bc87-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> `IAppDomainSetup` <span data-ttu-id="7bc87-104">만들어지기 전에 응용 프로그램 도메인의 측면을 구성 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-104">provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bc87-105">구문</span><span class="sxs-lookup"><span data-stu-id="7bc87-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bc87-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bc87-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="7bc87-107">[out] 에 대 한 인터페이스 포인터를 <xref:System.AppDomainSetup?displayProperty=nameWithType> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7bc87-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="7bc87-108">형식의이 매개 변수를 `IUnknown`호출자에 게 일반적으로 호출 해야 하므로 `QueryInterface` 형식의 인터페이스 포인터를 가져오려면이 포인터에 대 한 `IAppDomainSetup`합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bc87-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="7bc87-109">Return Value</span></span>  
  
|<span data-ttu-id="7bc87-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7bc87-110">HRESULT</span></span>|<span data-ttu-id="7bc87-111">설명</span><span class="sxs-lookup"><span data-stu-id="7bc87-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7bc87-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7bc87-112">S_OK</span></span>|<span data-ttu-id="7bc87-113">작업에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-113">The operation was successful.</span></span>|  
|<span data-ttu-id="7bc87-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7bc87-114">S_FALSE</span></span>|<span data-ttu-id="7bc87-115">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="7bc87-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7bc87-116">E_FAIL</span></span>|<span data-ttu-id="7bc87-117">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="7bc87-118">E_FAIL을 반환 하는 메서드는 CLR (공용 언어 런타임) 더 이상 사용할 수 진행에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="7bc87-119">호스팅 Api에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7bc87-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7bc87-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7bc87-121">CLR이 로드 된 프로세스에 또는 CLR 상태인는 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bc87-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7bc87-122">설명</span><span class="sxs-lookup"><span data-stu-id="7bc87-122">Remarks</span></span>  
 <span data-ttu-id="7bc87-123">이 메서드에서 반환 된 포인터는 일반적으로 매개 변수로 전달 된 [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="7bc87-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bc87-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bc87-124">Requirements</span></span>  
 <span data-ttu-id="7bc87-125">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7bc87-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bc87-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7bc87-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bc87-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7bc87-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bc87-128">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7bc87-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc87-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="7bc87-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="7bc87-130">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bc87-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
