---
title: ICLRDomainManager::SetAppDomainManagerType 메서드
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
ms.openlocfilehash: 5c61e2e1208cec0bda1492964a8d02bd71f5a1c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129326"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="9627c-102">ICLRDomainManager::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="9627c-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="9627c-103">기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자의 <xref:System.AppDomainManager?displayProperty=nameWithType> 클래스에서 파생 된 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9627c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9627c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9627c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9627c-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="9627c-106">진행 응용 프로그램 도메인 관리자 유형을 포함 하는 어셈블리의 표시 이름입니다. 예: "AdMgrExample, Version = 1.0.0.0, Culture = 중립, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="9627c-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="9627c-107">진행 네임 스페이스를 포함 하는 응용 프로그램 도메인 관리자의 유형 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="9627c-108">진행 응용 프로그램 도메인 관리자에 대 한 정보를 제공 하는 [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9627c-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="9627c-109">Return Value</span></span>  
 <span data-ttu-id="9627c-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9627c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9627c-111">HRESULT</span></span>|<span data-ttu-id="9627c-112">설명</span><span class="sxs-lookup"><span data-stu-id="9627c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9627c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9627c-113">S_OK</span></span>|<span data-ttu-id="9627c-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="9627c-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9627c-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9627c-116">CLR (공용 언어 런타임)이 프로세스에 로드 되지 않았거나 CLR이 관리 코드를 실행할 수 없거나 호출을 성공적으로 처리할 수 없는 상태에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9627c-117">주의</span><span class="sxs-lookup"><span data-stu-id="9627c-117">Remarks</span></span>  
 <span data-ttu-id="9627c-118">현재 `dwInitializeDomainFlags`에 대해 정의 된 유일한 값은 `eInitializeNewDomainFlags_NoSecurityChanges`입니다 .이 값은 CLR (공용 언어 런타임)에 게 응용 프로그램 도메인 관리자가 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드를 실행 하는 동안 보안 설정을 수정 하지 않도록 지시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9627c-119">이렇게 하면 CLR에서 조건부 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) 특성을 포함 하는 어셈블리의 로드를 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="9627c-120">이로 인해이 어셈블리 집합의 전이적 클로저가 큰 경우 시작 시간이 크게 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9627c-121">호스트에서 응용 프로그램 도메인 관리자에 대 한 `eInitializeNewDomainFlags_NoSecurityChanges`를 지정 하는 경우 응용 프로그램 도메인의 보안을 수정 하려고 시도 하면 <xref:System.InvalidOperationException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="9627c-122">[ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)메서드 호출은 `eInitializeNewDomainFlags_None`를 사용 하 여 `ICLRDomainManager::SetAppDomainManagerType`를 호출 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9627c-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9627c-123">Requirements</span></span>  
 <span data-ttu-id="9627c-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9627c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9627c-125">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="9627c-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9627c-126">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9627c-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9627c-127">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9627c-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9627c-128">참조</span><span class="sxs-lookup"><span data-stu-id="9627c-128">See also</span></span>

- [<span data-ttu-id="9627c-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="9627c-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="9627c-130">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9627c-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="9627c-131">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="9627c-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
