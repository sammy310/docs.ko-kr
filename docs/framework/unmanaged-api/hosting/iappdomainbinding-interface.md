---
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
ms.openlocfilehash: 652739ad51e0a177f7b0fc6c0c9a11508c820bb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721727"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="854a3-102">IAppDomainBinding 인터페이스</span><span class="sxs-lookup"><span data-stu-id="854a3-102">IAppDomainBinding Interface</span></span>

<span data-ttu-id="854a3-103">응용 프로그램 도메인이 생성 되었음을 호스트 응용 프로그램에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 되는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="854a3-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="854a3-104">메서드</span><span class="sxs-lookup"><span data-stu-id="854a3-104">Methods</span></span>  
  
|<span data-ttu-id="854a3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="854a3-105">Method</span></span>|<span data-ttu-id="854a3-106">설명</span><span class="sxs-lookup"><span data-stu-id="854a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="854a3-107">OnAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="854a3-107">OnAppDomain Method</span></span>](iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="854a3-108">응용 프로그램 도메인이 생성 되었음을 호스트에 알리기 위해 CLR (공용 언어 런타임)에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="854a3-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="854a3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="854a3-109">Requirements</span></span>  

 <span data-ttu-id="854a3-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="854a3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="854a3-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="854a3-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="854a3-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="854a3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="854a3-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="854a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="854a3-114">참조</span><span class="sxs-lookup"><span data-stu-id="854a3-114">See also</span></span>

- [<span data-ttu-id="854a3-115">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="854a3-115">Hosting Interfaces</span></span>](hosting-interfaces.md)
