---
description: '자세히 알아보기: IAppDomainSetup 인터페이스'
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
ms.openlocfilehash: 8fd224308ea68f7b56ae174c7f71fc4f89630101
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760586"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="1d28b-103">IAppDomainSetup 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d28b-103">IAppDomainSetup Interface</span></span>

<span data-ttu-id="1d28b-104"><xref:System.AppDomain?displayProperty=nameWithType> [ICorRuntimeHost:: CreateDomainEx](icorruntimehost-createdomainex-method.md) 메서드를 호출 하기 전에 호스트가 형식을 구성할 수 있도록 하는 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-104">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1d28b-105">속성</span><span class="sxs-lookup"><span data-stu-id="1d28b-105">Properties</span></span>  
  
|<span data-ttu-id="1d28b-106">속성</span><span class="sxs-lookup"><span data-stu-id="1d28b-106">Property</span></span>|<span data-ttu-id="1d28b-107">설명</span><span class="sxs-lookup"><span data-stu-id="1d28b-107">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="1d28b-108">응용 프로그램을 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-108">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="1d28b-109">애플리케이션의 이름을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-109">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="1d28b-110">파일을 섀도 복사한 응용 프로그램 관련 영역의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-110">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="1d28b-111">응용 프로그램에 대 한 구성 파일의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-111">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="1d28b-112">동적으로 생성 된 파일이 저장 되 고 액세스 되는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-112">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="1d28b-113">이 도메인에 연결 된 라이선스 파일의 경로를 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-113">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="1d28b-114">전용 어셈블리를 조사할 디렉터리와 결합 된 디렉터리의 목록을 가져오거나 설정 합니다 <xref:System.AppDomainSetup.ApplicationBase%2A> .</span><span class="sxs-lookup"><span data-stu-id="1d28b-114">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="1d28b-115"><xref:System.AppDomainSetup.ApplicationBase%2A>응용 프로그램의 검색 경로에서를 포함 하거나 제외 하는 문자열 값을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-115">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="1d28b-116">섀도 복사할 어셈블리가 들어 있는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-116">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="1d28b-117">섀도 복사를 설정 하거나 해제할지 여부를 나타내는 문자열을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-117">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="1d28b-118">유효한 값은 "true" 또는 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-118">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d28b-119">설명</span><span class="sxs-lookup"><span data-stu-id="1d28b-119">Remarks</span></span>  

 <span data-ttu-id="1d28b-120">인터페이스는 형식이 구현 하는 `IAppDomainSetup` 관리 되는 인터페이스에 해당 합니다 <xref:System.IAppDomainSetup> <xref:System.AppDomainSetup> .</span><span class="sxs-lookup"><span data-stu-id="1d28b-120">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="1d28b-121"><xref:System.IAppDomainSetup?displayProperty=nameWithType>해당 속성에 대 한 자세한 설명은를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d28b-121">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="1d28b-122">`IAppDomainSetup` 생성 하기 전에 인스턴스에 추가할 수 있는 어셈블리 바인딩 정보를 나타냅니다 <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="1d28b-122">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="1d28b-123">예를 들어 호스트는 속성을 설정 <xref:System.AppDomainSetup.ApplicationBase%2A> 하 여 CLR (공용 언어 런타임)에서 관리 되는 어셈블리를 검색 하는 루트 디렉터리를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-123">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d28b-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d28b-124">Requirements</span></span>  

 <span data-ttu-id="1d28b-125">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d28b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d28b-126">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1d28b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d28b-127">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d28b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d28b-128">**.NET Framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d28b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d28b-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d28b-129">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="1d28b-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d28b-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
