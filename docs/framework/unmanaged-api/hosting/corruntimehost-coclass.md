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
ms.openlocfilehash: 512009e053605e2018f1fcbafa422c1a36ddecc1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136902"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="23a4c-102">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="23a4c-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="23a4c-103">공용 언어 런타임에서 실행 되는 응용 프로그램을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23a4c-104">구문</span><span class="sxs-lookup"><span data-stu-id="23a4c-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="23a4c-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="23a4c-105">Interfaces</span></span>  
  
|<span data-ttu-id="23a4c-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="23a4c-106">Interface</span></span>|<span data-ttu-id="23a4c-107">설명</span><span class="sxs-lookup"><span data-stu-id="23a4c-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="23a4c-108">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23a4c-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="23a4c-109">CLR (공용 언어 런타임)을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="23a4c-110">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23a4c-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="23a4c-111">호스트에서 공용 언어 런타임을 명시적으로 시작 및 중지 하 고, 응용 프로그램 도메인을 만들고 구성 하 고, 기본 도메인에 액세스 하 고, 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="23a4c-112">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23a4c-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="23a4c-113">디버깅 서비스의 상태에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="23a4c-114">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23a4c-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="23a4c-115">가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="23a4c-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="23a4c-116">"IValidator"</span></span>|<span data-ttu-id="23a4c-117">이식 가능한 실행 가능한 이미지의 유효성을 검사 하 고 유효성 검사 오류에 대 한 자세한 보고 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23a4c-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23a4c-118">Requirements</span></span>  
 <span data-ttu-id="23a4c-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23a4c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23a4c-120">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="23a4c-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="23a4c-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23a4c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23a4c-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23a4c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a4c-123">참조</span><span class="sxs-lookup"><span data-stu-id="23a4c-123">See also</span></span>

- [<span data-ttu-id="23a4c-124">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="23a4c-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
