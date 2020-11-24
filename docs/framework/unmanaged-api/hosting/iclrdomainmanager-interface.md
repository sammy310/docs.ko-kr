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
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681173"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="11768-102">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11768-102">ICLRDomainManager Interface</span></span>

<span data-ttu-id="11768-103">호스트에서 기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자를 지정 하 고 초기화 속성을 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11768-104">메서드</span><span class="sxs-lookup"><span data-stu-id="11768-104">Methods</span></span>  
  
|<span data-ttu-id="11768-105">메서드</span><span class="sxs-lookup"><span data-stu-id="11768-105">Method</span></span>|<span data-ttu-id="11768-106">설명</span><span class="sxs-lookup"><span data-stu-id="11768-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11768-107">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="11768-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="11768-108"><xref:System.AppDomainManager?displayProperty=nameWithType>기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 응용 프로그램 도메인 관리자의 클래스에서 파생 된 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="11768-109">SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="11768-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="11768-110">기본 응용 프로그램 도메인을 초기화 하는 데 사용 되는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11768-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11768-111">설명</span><span class="sxs-lookup"><span data-stu-id="11768-111">Remarks</span></span>  

 <span data-ttu-id="11768-112">이 인터페이스의 인스턴스를 가져오려면 관리자 유형 IID를 사용 하 여 [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) 메서드를 호출 합니다 `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="11768-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11768-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11768-113">Requirements</span></span>  

 <span data-ttu-id="11768-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11768-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11768-115">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="11768-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="11768-116">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11768-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11768-117">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11768-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11768-118">참조</span><span class="sxs-lookup"><span data-stu-id="11768-118">See also</span></span>

- [<span data-ttu-id="11768-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11768-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="11768-120">호스팅</span><span class="sxs-lookup"><span data-stu-id="11768-120">Hosting</span></span>](index.md)
