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
ms.openlocfilehash: b1e595e1a4f1b462437f47207b998829a8bd774d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129459"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="9d443-102">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="9d443-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="9d443-103">런타임에의 한 코드 실행을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d443-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d443-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d443-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="9d443-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d443-105">Interfaces</span></span>  
  
|<span data-ttu-id="9d443-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d443-106">Interface</span></span>|<span data-ttu-id="9d443-107">설명</span><span class="sxs-lookup"><span data-stu-id="9d443-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="9d443-108">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d443-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="9d443-109">런타임에의 한 응용 프로그램 실행을 제어 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d443-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="9d443-110">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d443-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="9d443-111">이식 가능한 실행 이미지의 유효성을 검사 하 고 유효성 검사 오류에 대 한 자세한 보고를 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d443-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d443-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d443-112">Requirements</span></span>  
 <span data-ttu-id="9d443-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d443-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d443-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9d443-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9d443-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d443-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d443-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d443-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d443-117">참조</span><span class="sxs-lookup"><span data-stu-id="9d443-117">See also</span></span>

- [<span data-ttu-id="9d443-118">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="9d443-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
