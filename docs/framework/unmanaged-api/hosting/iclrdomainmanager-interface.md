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
ms.openlocfilehash: aa874205cf14232e7a69ed2215086e33c0beab4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129337"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="5dcc8-102">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5dcc8-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="5dcc8-103">호스트에서 기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자를 지정 하 고 초기화 속성을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dcc8-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5dcc8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5dcc8-104">Methods</span></span>  
  
|<span data-ttu-id="5dcc8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5dcc8-105">Method</span></span>|<span data-ttu-id="5dcc8-106">설명</span><span class="sxs-lookup"><span data-stu-id="5dcc8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5dcc8-107">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="5dcc8-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="5dcc8-108">기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자의 <xref:System.AppDomainManager?displayProperty=nameWithType> 클래스에서 파생 된 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dcc8-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="5dcc8-109">SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5dcc8-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="5dcc8-110">기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dcc8-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dcc8-111">주의</span><span class="sxs-lookup"><span data-stu-id="5dcc8-111">Remarks</span></span>  
 <span data-ttu-id="5dcc8-112">이 인터페이스의 인스턴스를 가져오려면 `IID_ICLRDomainManager`관리자 형식 IID를 사용 하 여 [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dcc8-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dcc8-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5dcc8-113">Requirements</span></span>  
 <span data-ttu-id="5dcc8-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5dcc8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dcc8-115">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="5dcc8-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5dcc8-116">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dcc8-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dcc8-117">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dcc8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dcc8-118">참조</span><span class="sxs-lookup"><span data-stu-id="5dcc8-118">See also</span></span>

- [<span data-ttu-id="5dcc8-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5dcc8-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5dcc8-120">호스팅</span><span class="sxs-lookup"><span data-stu-id="5dcc8-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
