---
title: IAppDomainSetup 인터페이스
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126866"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="6a5ad-102">IAppDomainSetup 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a5ad-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="6a5ad-103">[ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드를 호출 하기 전에 호스트에서 <xref:System.AppDomain?displayProperty=nameWithType> 형식을 구성할 수 있도록 하는 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6a5ad-104">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="6a5ad-104">Properties</span></span>  
  
|<span data-ttu-id="6a5ad-105">속성</span><span class="sxs-lookup"><span data-stu-id="6a5ad-105">Property</span></span>|<span data-ttu-id="6a5ad-106">설명</span><span class="sxs-lookup"><span data-stu-id="6a5ad-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="6a5ad-107">응용 프로그램을 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="6a5ad-108">애플리케이션의 이름을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="6a5ad-109">파일을 섀도 복사한 응용 프로그램 관련 영역의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="6a5ad-110">응용 프로그램에 대 한 구성 파일의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="6a5ad-111">동적으로 생성 된 파일이 저장 되 고 액세스 되는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="6a5ad-112">이 도메인에 연결 된 라이선스 파일의 경로를 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="6a5ad-113">전용 어셈블리를 조사할 <xref:System.AppDomainSetup.ApplicationBase%2A> 디렉터리와 결합 된 디렉터리의 목록을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="6a5ad-114">응용 프로그램의 검색 경로에서 <xref:System.AppDomainSetup.ApplicationBase%2A>를 포함 하거나 제외 하는 문자열 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="6a5ad-115">섀도 복사할 어셈블리가 들어 있는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="6a5ad-116">섀도 복사를 설정 하거나 해제할지 여부를 나타내는 문자열을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="6a5ad-117">유효한 값은 "true" 또는 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a5ad-118">주의</span><span class="sxs-lookup"><span data-stu-id="6a5ad-118">Remarks</span></span>  
 <span data-ttu-id="6a5ad-119">`IAppDomainSetup` 인터페이스는 <xref:System.AppDomainSetup> 형식이 구현 하는 관리 되는 <xref:System.IAppDomainSetup> 인터페이스에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="6a5ad-120">해당 속성에 대 한 자세한 설명은 <xref:System.IAppDomainSetup?displayProperty=nameWithType>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="6a5ad-121">`IAppDomainSetup` 생성 하기 전에 <xref:System.AppDomain> 인스턴스에 추가할 수 있는 어셈블리 바인딩 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="6a5ad-122">예를 들어 호스트는 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성을 설정 하 여 CLR (공용 언어 런타임)에서 관리 되는 어셈블리를 검색 하는 루트 디렉터리를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5ad-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a5ad-123">Requirements</span></span>  
 <span data-ttu-id="6a5ad-124">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a5ad-125">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6a5ad-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a5ad-126">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5ad-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a5ad-127">**.NET Framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a5ad-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5ad-128">참조</span><span class="sxs-lookup"><span data-stu-id="6a5ad-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="6a5ad-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a5ad-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
