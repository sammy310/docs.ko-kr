---
title: IHostControl 인터페이스
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 9dd89abb332853b966aa81dc506099b7af6ca3b2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804929"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="ef4bf-102">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef4bf-102">IHostControl Interface</span></span>
<span data-ttu-id="ef4bf-103">어셈블리 로드를 구성 하 고 호스트가 지 원하는 호스팅 인터페이스를 결정 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4bf-103">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef4bf-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ef4bf-104">Methods</span></span>  
  
|<span data-ttu-id="ef4bf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ef4bf-105">Method</span></span>|<span data-ttu-id="ef4bf-106">Description</span><span class="sxs-lookup"><span data-stu-id="ef4bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef4bf-107">GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="ef4bf-107">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="ef4bf-108">지정 된을 사용 하 여 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="ef4bf-108">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="ef4bf-109">SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="ef4bf-109">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="ef4bf-110">응용 프로그램 도메인이 생성 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ef4bf-110">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef4bf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef4bf-111">Requirements</span></span>  
 <span data-ttu-id="ef4bf-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef4bf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef4bf-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="ef4bf-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef4bf-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef4bf-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef4bf-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef4bf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4bf-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef4bf-116">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="ef4bf-117">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef4bf-117">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="ef4bf-118">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef4bf-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ef4bf-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ef4bf-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
