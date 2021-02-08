---
description: '자세히 알아보기: ICorRuntimeHost:: CreateDomainSetup 메서드'
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
ms.openlocfilehash: b7c2dc55fa9f0d3d5a5c18e38c2c825048ae5f53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789686"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="b8755-103">ICorRuntimeHost::CreateDomainSetup 메서드</span><span class="sxs-lookup"><span data-stu-id="b8755-103">ICorRuntimeHost::CreateDomainSetup Method</span></span>

<span data-ttu-id="b8755-104">인스턴스에 IAppDomainSetup 형식의 인터페이스 포인터를 가져옵니다 <xref:System.AppDomainSetup?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b8755-104">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="b8755-105">`IAppDomainSetup` 응용 프로그램 도메인을 만들기 전에 요소를 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-105">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8755-106">구문</span><span class="sxs-lookup"><span data-stu-id="b8755-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8755-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8755-107">Parameters</span></span>  

 `pAppDomainSetup`  
 <span data-ttu-id="b8755-108">제한이 인스턴스에 대 한 인터페이스 포인터 <xref:System.AppDomainSetup?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-108">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="b8755-109">이 매개 변수는로 형식화 `IUnknown` 되므로 호출자는 일반적으로 `QueryInterface` 이 포인터에서를 호출 하 여 형식의 인터페이스 포인터를 가져와야 합니다 `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="b8755-109">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8755-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="b8755-110">Return Value</span></span>  
  
|<span data-ttu-id="b8755-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b8755-111">HRESULT</span></span>|<span data-ttu-id="b8755-112">설명</span><span class="sxs-lookup"><span data-stu-id="b8755-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b8755-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b8755-113">S_OK</span></span>|<span data-ttu-id="b8755-114">작업이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-114">The operation was successful.</span></span>|  
|<span data-ttu-id="b8755-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b8755-115">S_FALSE</span></span>|<span data-ttu-id="b8755-116">작업을 완료 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-116">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b8755-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b8755-117">E_FAIL</span></span>|<span data-ttu-id="b8755-118">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-118">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b8755-119">메서드가 E_FAIL 반환 하는 경우 해당 프로세스에서 CLR (공용 언어 런타임)을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-119">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b8755-120">호스팅 Api에 대 한 후속 호출은 HOST_E_CLRNOTAVAILABLE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-120">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b8755-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b8755-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b8755-122">CLR이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8755-123">설명</span><span class="sxs-lookup"><span data-stu-id="b8755-123">Remarks</span></span>  

 <span data-ttu-id="b8755-124">이 메서드에서 반환 된 포인터는 일반적으로 [Createdomainex](icorruntimehost-createdomainex-method.md) 메서드에 매개 변수로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-124">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8755-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b8755-125">Requirements</span></span>  

 <span data-ttu-id="b8755-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8755-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8755-127">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b8755-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b8755-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8755-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8755-129">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b8755-129">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8755-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8755-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="b8755-131">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b8755-131">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
