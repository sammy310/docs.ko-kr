---
title: CLRRuntimeHost Coclass
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207762"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="f63e5-102">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="f63e5-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="f63e5-103">런타임에서 코드 실행을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63e5-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f63e5-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="f63e5-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="f63e5-105">Interfaces</span></span>  
  
|<span data-ttu-id="f63e5-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="f63e5-106">Interface</span></span>|<span data-ttu-id="f63e5-107">설명</span><span class="sxs-lookup"><span data-stu-id="f63e5-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="f63e5-108">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f63e5-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="f63e5-109">런타임에서 응용 프로그램의 실행을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63e5-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="f63e5-110">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f63e5-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="f63e5-111">이식 가능한 실행 가능 이미지의 유효성 검사 및 유효성 검사 오류를 자세히 보고 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f63e5-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f63e5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f63e5-112">Requirements</span></span>  
 <span data-ttu-id="f63e5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f63e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f63e5-114">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f63e5-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f63e5-115">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f63e5-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f63e5-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f63e5-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f63e5-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="f63e5-117">See also</span></span>

- [<span data-ttu-id="f63e5-118">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="f63e5-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
