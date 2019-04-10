---
title: CorRuntimeHost Coclass
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218565"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="5a997-102">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="5a997-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="5a997-103">공용 언어 런타임에서 실행 되는 응용 프로그램 관리에 대 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a997-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a997-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a997-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="5a997-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a997-105">Interfaces</span></span>  
  
|<span data-ttu-id="5a997-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a997-106">Interface</span></span>|<span data-ttu-id="5a997-107">설명</span><span class="sxs-lookup"><span data-stu-id="5a997-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="5a997-108">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a997-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="5a997-109">CLR (공용 언어 런타임) 구성 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a997-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="5a997-110">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a997-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="5a997-111">시작 하 고 만들고 기본 도메인에 액세스 하 고 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 응용 프로그램 도메인을 구성 하려면 공용 언어 런타임을 명시적으로 중지할 호스트를 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a997-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="5a997-112">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a997-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="5a997-113">디버깅 서비스의 상태에 대 한 정보를 가져오기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a997-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="5a997-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a997-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="5a997-115">가비지 컬렉션 시스템에 대 한 정보를 얻기 위한 고 가비지 컬렉션의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a997-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="5a997-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="5a997-116">"IValidator"</span></span>|<span data-ttu-id="5a997-117">이식 가능한 실행 가능 이미지의 유효성 검사 및 유효성 검사 오류를 자세히 보고에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a997-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a997-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a997-118">Requirements</span></span>  
 <span data-ttu-id="5a997-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5a997-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a997-120">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5a997-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5a997-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5a997-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5a997-122">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="5a997-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a997-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a997-123">See also</span></span>

- [<span data-ttu-id="5a997-124">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="5a997-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
