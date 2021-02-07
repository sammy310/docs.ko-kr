---
description: '자세히 알아보기: IAppDomainBinding 인터페이스'
title: IAppDomainBinding 인터페이스
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
ms.openlocfilehash: 3de559af023311f705f9f7dc6eb9785788216a83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760617"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="40dc3-103">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40dc3-103">IAppDomainBinding Interface</span></span>

<span data-ttu-id="40dc3-104">응용 프로그램 도메인이 생성 되었음을 호스트 응용 프로그램에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 되는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="40dc3-104">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40dc3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="40dc3-105">Methods</span></span>  
  
|<span data-ttu-id="40dc3-106">메서드</span><span class="sxs-lookup"><span data-stu-id="40dc3-106">Method</span></span>|<span data-ttu-id="40dc3-107">설명</span><span class="sxs-lookup"><span data-stu-id="40dc3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40dc3-108">OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="40dc3-108">OnAppDomain Method</span></span>](iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="40dc3-109">응용 프로그램 도메인이 생성 되었음을 호스트에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40dc3-109">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40dc3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40dc3-110">Requirements</span></span>  

 <span data-ttu-id="40dc3-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40dc3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40dc3-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="40dc3-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40dc3-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40dc3-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40dc3-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40dc3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40dc3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40dc3-115">See also</span></span>

- [<span data-ttu-id="40dc3-116">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40dc3-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
