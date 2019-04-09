---
title: ICLRDomainManager 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53149b92ca40ad50ecbefaf4701940e8567ae5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103926"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="b6cba-102">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6cba-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="b6cba-103">호스트를에서 기본 응용 프로그램 도메인을 초기화 하 고 초기화 속성을 지정 하는 응용 프로그램 도메인 관리자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6cba-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6cba-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b6cba-104">Methods</span></span>  
  
|<span data-ttu-id="b6cba-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b6cba-105">Method</span></span>|<span data-ttu-id="b6cba-106">설명</span><span class="sxs-lookup"><span data-stu-id="b6cba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6cba-107">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="b6cba-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="b6cba-108">파생 된 유형을 지정 합니다 <xref:System.AppDomainManager?displayProperty=nameWithType> 기본 응용 프로그램 도메인을 초기화 하는 데 사용할 응용 프로그램 도메인 관리자의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b6cba-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="b6cba-109">SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="b6cba-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="b6cba-110">기본 응용 프로그램 도메인을 초기화 하는 데 사용할 수 있는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cba-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6cba-111">설명</span><span class="sxs-lookup"><span data-stu-id="b6cba-111">Remarks</span></span>  
 <span data-ttu-id="b6cba-112">이 인터페이스의 인스턴스를 가져오려면 호출 합니다 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) manager 형식 IID 사용 하 여 메서드 `IID_ICLRDomainManager`합니다.</span><span class="sxs-lookup"><span data-stu-id="b6cba-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6cba-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6cba-113">Requirements</span></span>  
 <span data-ttu-id="b6cba-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6cba-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6cba-115">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b6cba-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b6cba-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b6cba-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b6cba-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b6cba-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b6cba-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="b6cba-118">See also</span></span>

- [<span data-ttu-id="b6cba-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6cba-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b6cba-120">호스팅</span><span class="sxs-lookup"><span data-stu-id="b6cba-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
