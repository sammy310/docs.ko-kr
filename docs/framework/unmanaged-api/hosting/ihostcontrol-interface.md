---
description: '자세히 알아보기: IHostControl 인터페이스'
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
ms.openlocfilehash: e7a242ed0fdaa734425bec9b48f01fe45cba5182
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789465"
---
# <a name="ihostcontrol-interface"></a><span data-ttu-id="c6924-103">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6924-103">IHostControl Interface</span></span>

<span data-ttu-id="c6924-104">어셈블리 로드를 구성 하 고 호스트가 지 원하는 호스팅 인터페이스를 결정 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6924-104">Provides methods for configuring the loading of assemblies, and for determining which hosting interfaces the host supports.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6924-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c6924-105">Methods</span></span>  
  
|<span data-ttu-id="c6924-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c6924-106">Method</span></span>|<span data-ttu-id="c6924-107">설명</span><span class="sxs-lookup"><span data-stu-id="c6924-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c6924-108">GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="c6924-108">GetHostManager Method</span></span>](ihostcontrol-gethostmanager-method.md)|<span data-ttu-id="c6924-109">지정 된을 사용 하 여 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID` .</span><span class="sxs-lookup"><span data-stu-id="c6924-109">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>|  
|[<span data-ttu-id="c6924-110">SetAppDomainManager 메서드</span><span class="sxs-lookup"><span data-stu-id="c6924-110">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)|<span data-ttu-id="c6924-111">응용 프로그램 도메인이 생성 되었음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c6924-111">Notifies the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6924-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6924-112">Requirements</span></span>  

 <span data-ttu-id="c6924-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6924-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6924-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c6924-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6924-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6924-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6924-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6924-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6924-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6924-117">See also</span></span>

- <xref:System.AppDomainManager>
- [<span data-ttu-id="c6924-118">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6924-118">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="c6924-119">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6924-119">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c6924-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c6924-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
